---
layout: post
title:  "Ruby on Rails Project: Using a Third-Party Authentication (OAuth)"
location: "New York City"
date:   2019-03-25 
categories: technology
photo: https://ludaires.github.io/img/hero-login-page.png
---
It is exciting to see how far and how many things we can build at the end of the Rails section.  For my Rails project, I kept working in the same domain from my Sinatra project. I continued my CMMS app for a chemical laboratory. It tracks all the equipment maintenances. 

The main difference from the Sinatra to Rails implementation can be seen not only in the UI but in the fairly amount of logic in the backend. As I learned more about best practices and software design principles, I was able to come up with a much cleaner version. I could refactor it using helpers, partials with locals, and nested forms.

As the title suggests, one of the requirements for this project was to use a third-party authentication solution. For that, I found [OmniAuth](https://omniauth.io/) as a great library to handle different authentication providers like Google.

## Google Authentication Setup

Here is a quick step-by-step, demonstrating how I set up my application. In addition to OmniAuth, I used another library called [OmniAuth Google OAuth2](https://github.com/zquestz/omniauth-google-oauth2). You can find the documentation [here](https://github.com/zquestz/omniauth-google-oauth2#usage). 

#### Gemfile

```ruby
gem 'omniauth-google-oauth2'
gem 'dotenv-rails'
```

#### Google API Setup

Go to [console developers]('https://console.developers.google.com') and select your project if you have already set up one. Go to Credentials, then select the "OAuth consent screen" tab on top, and provide an 'EMAIL ADDRESS' and a 'PRODUCT NAME'.

> Because I didn't know all details for creating a new project in Google Console, I followed this excellent blog post explaining [how to create a Google API Console project and OAuth2 Client ID](https://o7planning.org/en/11123/creating-a-google-api-console-project-and-oauth2-client-id).


#### OmniAuth with Google

Create a file at `config/initializers/omniauth.rb` with the following code:

```ruby
Rails.application.config.middleware.use OmniAuth::Builder do
    provider :google_oauth2, ENV['GOOGLE_CLIENT_ID'], ENV['GOOGLE_CLIENT_SECRET']
end 
```

#### Environment Variables

Create a `.env` file in your root application and include the 'dotenv-rails' library to load the config into the ENV hash. Don't forget to add the `.env` file to your `.gitignore` to ensure you don't commit your credentials. You don't want to expose your credentials to strangers, right? 

```ruby
GOOGLE_CLIENT_ID="<paste your client_id keys here>"
GOOGLE_CLIENT_SECRET="<paste your client_secret here>"
```

#### Link to Login

If you have a navigation bar, create a link to login. In my case, I included the following link at `app/views/layouts/application.html.erb`:

```html
<%= link_to "Log in via Google", '/auth/google_oauth2', class: "btn btn-outline-secondary" %>
```


#### Routing OAuth Flow in Your Application

In my `config/routes.rb` file:

```
get '/auth/google_oauth2/callback', to: 'sessions#create_from_omniauth'
```

#### User Sessions

In my `app/models/user.rb` file, I included a method that finds or create new users from Google Authentication. It assigns them a random password if new. 
    
```ruby
def self.create_from_google(auth)
    User.find_or_create_by(email: auth[:info][:email]) do |user|
        user.username = auth[:info][:name]
        user.password = SecureRandom.hex
    end
end
```

In my `app/controllers/sessions_controller.rb`:

```ruby
def create_from_omniauth
    @user = User.create_from_google(auth)
    set_session
    if logged_in?
        flash[:message] = "Successfully authenticated via Google!"
        redirect_to user_path(@user)
    else
        flash[:message] = "Something went wrong. Try again"
        redirect_to root_path
    end
end

private
def auth
    request.env['omniauth.auth']
end
```

You can find the source code at [maintenance_management_rails_app](https://github.com/ludaires/maintenance_management_rails_app).

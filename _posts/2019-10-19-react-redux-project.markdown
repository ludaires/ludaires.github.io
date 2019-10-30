---
layout: post
title:  "React Redux Project: Single Page Application"
location: "New York City"
date:   2019-10-19
categories: technology
photo: https://ludaires.github.io/img/react-redux.png
---
How exciting is to get at the end of the curriculum. I have learned so much and could build many cool projects. The projects have helped me understand the sections and how to apply all the knowledge I have acquired, and  go even further exploring different libraries. 

As a mother, I discovery it can be very challenge to find daycare for my daughter. I had decided to build a tool to help parents to get track of daycares they have visit, keep notes, schedule visits, and finally choose the one that best fits the needs of their kids. 

In my application I used [Yelp Fusion API](https://www.yelp.com/fusion) to search for daycares by zip code. I called two endpoints to get the businesses and reviews. For my backend I built a Rails API to handle the data persistence. To serializer fast I choosed the [Netflix/fast_jsonapi: A lightning fast JSON:API.](https://github.com/Netflix/fast_jsonapi) API as a serializer for Ruby Objects, since it has a better benchmark times for 250 records than Active Model Serializer. 

My front-end was built using React and Redux to manage state.  Understanding the redux flow is very important to manage state properly. Bellow is a simple graphic to understand the redux cycle. 

![Redux diagram](img/redux_diagram.png)

This time to design my application I decided to use the framework [Material-UI](https://material-ui.com/getting-started/installation/).It is very well documented with tons of usage examples. 

You can see my [frontend](https://github.com/ludaires/find-daycare-frontend) and [backend](https://github.com/ludaires/find-daycare-backend) repository on github.  
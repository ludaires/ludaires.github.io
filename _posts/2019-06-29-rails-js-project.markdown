---
layout: post
title:  "Rails JavaScript Project: Introduction to Single Page Application"
location: "New York City"
date:   2019-06-29
categories: technology
photo: https://ludaires.github.io/img/spa-icon.jpg
---
Last week at my coding Bootcamp, I was asked to implement a project for the section "Rails with Javascript." It required adding dynamic features using Javascript and an API based on JSON.

## Quick Intro

Previously, I had created a Maintenance Management System for Laboratories (CMMS). It is supposed to help technicians to keep track of all records and assets that they are responsible for in a laboratory. That is, it includes features like schedules, maintenance records, tasks, and a long history of all work these technicians performed. In a chemical lab, for example, many pieces of equipment require periodic maintenance, such as corrective and preventive types.

The project was primarily built to render ERB views on the server-side. It did not include any JSON endpoints.

## Hybrid Approach: Moving from Server to Client

Previously, by the time I created my Rails app, I had implemented a few basic functionalities, including the basic models, a couple of controllers and views. These were all server rendered, using Views and ERB templates. This time I would like to move *from server to client rendered pages*. That's when the concept of single-page apps comes in handy. 

To expand the app, I'd decided to use a hybrid approach. Instead of migrating the current code, only the new features should support AJAX requests and JSON responses.
Like in the Equipment Controller 

![Equipment Controller](/img/equipment_controller.png)

## The Idea: Simulate a Single-Page Application (SPA) 

[SPA](https://en.wikipedia.org/wiki/Single-page_application) is a web application or web site that interacts with the user by dynamically rewriting the current page rather than loading entire new pages from a server. This approach avoids interruption of the user experience between successive pages, making the application behave more like a desktop application.

In a SPA, it is common that all the necessary code - HTML, Javascript, and CSS - is retrieved in a single page load.

The most prominent technique used to load dynamic content is AJAX. It allows rendering of fluid web views without constant page reloads. 

Sending the app data in JSON creates a separation between static from dynamic content. The presentation layer - HTML, CSS - is treated as static, and the application logic - AJAX, JSON - dynamic. This separation makes the app easier to maintain. In a well-architected SPA, you can change the whole presentation in HTML (static) without touching the code that implements the business logic (dynamic).

![Application Lifecycle](/img/app_lifecycle.png)

## Practical Example

![Form](/img/ajax_form.png)

![Equipment Controller](/img/equipment_controller_ new.png)

In theory, this hybrid approach is supposed to make my application more scalable and easier to maintain. Next, I should be able to replace all server rendered forms by a full SPA like [Angular](https://angular.io/) or [React](https://reactjs.org/).

## Reference

Source Code: https://github.com/ludaires/maintenance-rails-js-project
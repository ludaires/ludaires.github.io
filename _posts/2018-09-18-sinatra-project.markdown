---
layout: post
title:  "CMMS with UML"
# location: "New York City"
date:   2018-09-18 
categories: technology
photo: https://ludaires.github.io/img/analises.jpg
---
As a former industrial chemist who decided to learn how to code, I wanted to create a project which could combine the two things I love the most: Chemistry and Coding. 

A chemical lab has a lot of equipment that needs periodic maintenance: corrective and preventive. I developed an app to help technicians to keep a record of all assets they are responsible for, including scheduling, track maintenance, tasks, and keeping a record of the work they perform.  

The web application was built in Ruby, using MVC architecture, and Sinatra. Here is a class diagram I put together in UML [Unified Modeling Language](https://en.wikipedia.org/wiki/Unified_Modeling_Language). I used [Lucidchart](https://www.lucidchart.com "Lucidchart's Homepage") to design the schema and set up everything beforehand. My primary goal was to make this app very simple and functional.

![Class Diagram](/img/class_diagram.png)

A class diagram is a type of static structure diagram that describes the structures of a system by showing the system’s classes, their attributes, methods and the relationships among objects.

In the diagram, classes are represented with boxes that contain up to three compartments:
The top compartment contains the name of the class
The middle compartment contains the attributes of the class
The bottom compartment contains the operations the class can execute. 

You can learn more about it [here](https://en.wikipedia.org/wiki/Class_diagram "Wikipedia") and how to create a class diagram is this great [Youtube video](https://youtu.be/UI6lqHOVHic "Youtube"). 

<iframe width="560" height="315" src="https://www.youtube.com/embed/UI6lqHOVHic" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

You can see the full application on my [GitHub account](https://github.com/ludaires/maintenance_management_sinatra_app "Ludmilla's GitHub"). 

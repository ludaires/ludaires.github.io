---
layout: post
title:  "Accessibility: Chrome DevTools"
location: "New York City"
date:   2019-10-24
categories: technology
photo: https://ludaires.github.io/img/accessibility.png
---
Did you know that roughly 15% of the world’s population has some form of [disability](https://www.who.int/en/news-room/fact-sheets/detail/disability-and-health){:target="_blank"}? I am talking about over 1 billion people. 

As a person who believes in diversity and inclusion, I always have this in mind when developing a new tool. For reference, W3 has a great guideline for [web content accessibility](https://www.w3.org/TR/WCAG20/){:target="_blank"}, and google DevTools can audit a website for accessibility either. More information about it [here](https://github.com/GoogleChrome/lighthouse){:target="_blank"}. 

## How to audit

Accessibility Reference and Tools for [Web Developers](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference){:target="_blank"} are a guideline made from Google on how to audit your application step by step. 

## Pratical Example

I used the audits on DevTools to verify my Find Daycare application and where I could improve to make it more accessible. 

![First Audit](/img/first-audit.png)

My background and foreground colors do not have a sufficient contrast ratio. I decided to change the colors and make the button text bold. 

![Second Audit](/img/second-audit.png)

Changing the style of my application increased my accessibility rate to 82. This tool doesn’t only show you what to improve; it has links to websites teaching you how to do it and why it is so important.

There is an excellent [YouTubecasts](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g){:target="_blank"} with Rob Dodson teaching accessibility fundamentals and how to audit applications. 

*A11ycasts is short for AccessibilityCasts (a11y is a common shortening of the term accessibility because there are 11 letters in between the “”A”” and the “”Y””). The goal of A11ycasts is to teach developers how accessibility works all the way down at the platform level, while also demonstrating real world accessibility problems and solutions to fix them.*

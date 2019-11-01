---
layout: post
title:  "React: Understanding setState()"
location: "New York City"
date:   2019-11-01
categories: technology
photo: https://ludaires.github.io/img/react-state.jpeg
---
A React class component has an internal state, which like props, affects how the component renders and behaves. Unlike accessories, the state is local to the component and can only be initialized and updated within it.

Remember that state is similar to props, but it is private and fully controlled by the component. 

## Three things to know about setState()

#### Do not  modify state directly ####
Modifying State directly will not re-render a component

#### State Updates May Be Asynchronous ####
React may batch multiple setState() calls at once for performance.  That’s the reason why we can’t rely on their values for calculating the next state. 

#### State Updates are Merged ####
Calling setState() merges the object you provide into the current state.

> * The merging process is kicking off what is called in React [reconciliation](https://reactjs.org/docs/reconciliation.html){:target="_blank"}. The reconciliation process is the way React updates the DOM, by making changes to the component based on the change in state. When the request to setState() is triggered, React creates a new tree containing the reactive elements in the component (along with the updated state). React knows which changes to implement and will only update the parts of the DOM where necessary. That's the reason why React is fast.


The most important thing to know about setState is the fact that it is a function in React that works asynchronous. That is why state are not immediately available after the update. 

Here a link to the official documentation to learn more about State and [Lifecyle](https://reactjs.org/docs/state-and-lifecycle.html){:target="_blank"}
---
layout: post
title: Library of angular 2-4-5  code example and snippets
published: true
---

### http interceptor to add a token to all outgoing request 

To make json web token authentication, we need to pass  token to the server. It is convenient to make this token logic independant of each api call so that it is global. An interceptor intercept all request outgoing or ingoing to make modification to them. So we can create a service that deal with interception. 

<script src="https://gist.github.com/sinsunsan/adba1f200f6a34165ae6b8ae8ab2e09f.js"></script>


### Action definition of angular ngrx architecture

The purpose of the action file is to define actions of which to take effects. 
In a typical page where we have to load specific data. We have 3 basics actions : 

* The page loading itself (start with On)
* The action of loading the data (start with Load)
* The action of receiving the data (end with Loaded)

An other convention used in this file is : 

* to end type representing object received from the server my MD. (Model data)
* To end type representing object sent to the server by TO (Transfer Object) 


<script src="https://gist.github.com/sinsunsan/d7ee9776e2b586d9b0a9f71f51b6a36e.js"></script>

### Define a async pipe thanks to ng-if

Allow to define a aync variable globally in a structural directive (*ngFor, *ngIf)

<script src="https://gist.github.com/sinsunsan/427696be90ba076437299b2f3bed0266.js"></script>


### Use a template variable inside a component class


Template variable #myvar is accessible in the component js, with @viewchild and elementRef. Here is an example code snippet.

<script src="https://gist.github.com/sinsunsan/3ac829ab31f93e83c19c0d67ba60b8ea.js"></script>
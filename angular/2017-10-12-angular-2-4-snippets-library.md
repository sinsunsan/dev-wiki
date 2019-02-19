---
layout: post
title: Library of angular 2-4-5  code example and snippets
published: true
---

# 2017-10-12-angular-2-4-snippets-library

## http interceptor to add a token to all outgoing request

To make json web token authentication, we need to pass token to the server. It is convenient to make this token logic independent of each api call so that it is global. An interceptor intercept all request outgoing or ingoing to make modification to them. So we can create a service that deal with interception.

## Action definition of angular ngrx architecture

The purpose of the action file is to define actions of which to take effects. In a typical page where we have to load specific data. We have 3 basics actions :

* The page loading itself \(start with On\)
* The action of loading the data \(start with Load\)
* The action of receiving the data \(end with Loaded\)

An other convention used in this file is :

* to end type representing object received from the server my MD. \(Model data\)
* To end type representing object sent to the server by TO \(Transfer Object\) 

## Define a async pipe thanks to ng-if

Allow to define an async variable globally in a structural directive \(_ngFor,_ ngIf\)

## Use a template variable inside a component class

Template variable \#myvar is accessible in the component js, with @viewchild and elementRef. Here is an example code snippet.


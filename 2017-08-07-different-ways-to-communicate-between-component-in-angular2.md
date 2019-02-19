---
layout: post
title: X ways to communicate between component in angular 2
published: false
---

# 2017-08-07-different-ways-to-communicate-between-component-in-angular2

## @input @output

## Subject observable in a service

## @Host\(\) && @Contentchildren\(\)

To be used when compoents child and parent work intrically together like a item component and a list item... and you want to make accessible from the exterior only the parent component for example

@Host allow to have access to the parent component within the child component. Instead of passing the data from parent to child thanks to @Input. It could be more convenient to use @Host\(\).

The advantages are :

* nothing to set in the templates... all is available

@ContentChildren is the contrary being able to access the child property from a parent component

## Angular + Redux

## Use services

Services are in angula a way to extract logic from the components to be used everywhere. Services are mostly used to get data from the API and as utility services to package data handling logic...or to provide utility like logging, web soket...

## Component that extend a parent component

```javascript
export class WidgetMessageComponent  extends WidgetComponent implements OnInit
```

This syntax use prototypal inheritance to make `WidgetMessageComponent` a sub class of `WidgetComponent`

Pratically :

* the @component decorator is not overridable 
* any properties, functions defined in inherited component is also available in the component that inherited it 
* when user constructor definition in child component \(the component that extend\) 

```javascript
constructor(
    private route: ActivatedRoute,
  ) {
    super();
  }
```


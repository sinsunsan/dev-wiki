---
layout: post
title: Start angular 2 now! Main differences from v1
published: true
---

# Angular2 main differences with angular 1

Angular 2 architecture have changed, but javascript too. The rise of ES6 is parallel to the release of angular 2. Angular choose to have dependencies on typescript though it is possible to use angular 2 without typescript

## Typescript

Typescript is a superset of ES6. It means it has all features of ES6 plus additional features. The main differentiating feature is typings hence the name typescript [https://www.typescriptlang.org](https://www.typescriptlang.org) But not only, it allows also to use the decorator syntax @ used by angular heavily.

At first I was not very enthusiastic to use Typescript, first because it is a software initiated by Microsoft and I kept with some bad opinions about this firm. But also because I kept with the idea typings was a thing for old fashioned java, c++ guys and was not useful in modern workflows.

I changed my mind, about Microsoft and about hard typings!

It could be really useful, and the best is that you can use it a lot or in a minimal way if you want. It allow you to intercept simple errors before compilation, which is not bad.

The drawbacks are :

* you can have bugs only caused by typings stuff....
* you need to compile back to a file readable by the browser but less readable by you. But anyway with ES6 we will be obliged to work like this, till ES6 will be readable directly in all browsers.

## System.js and ES6 stuff

### The ES6 modules

ES6 typescript introduce the javascript modules syntax `import { myModule} from '../../file.js';`

It is nice because it allow to define what each files need in a declarative style. The previous way to do that, was simply to add many scripts files in a html fil. Or concatenate a bunch of files in one files. But no explicit relations was set between those files.

With the modules, every file "require" / "import" the files it need to execute properly. If you practice Node.js you should be familiar with that and the really simple idea it is.

### **You need a package loader!**

### **ES6 is not only syntax changes**

## Components everywhere

### Components angular clear syntax

The component syntax is much, much clearer that in angular 1. By the way everything is component. That mean that no part of the page rendered by angular is not a component. That does not mean you need to over structure your app, with components, sub-components. It is up to you to be granular as it is useful for you

### Css scoping / Web component like pseudo phantom DOM

Angular 2 introduce an elegant way to use component specific / phantom dom, without waiting for full browser support. Let's reacall what it is. Phantom DOM is a way to isolate the DOM of a component from the interior world so that global CSS do not impact it.

Let's take a simple example. You have a sidebar component, with it's style that you want everyone on the planet to be able to use, and also be sure that it's graphical appearance will be preserved.

Without phantom DOM, it is feasible, but you cannot garanty that the appearance of your component will be always preserved. Indeed the only way to style it in a secure way is to use a sort of name spacing with your component css.

```css
. complicated-and-specic-name_body {   
   background: blue; 
}
```

But there is always a way to override in the site where it is used. Only with iframe we can achieve this independance of component.

With phantom DOM, we can as the DOM inside the component, in a similar way than the iframe DOM, is not accessible and targetable by css rules from the exterior.

The problem is the phantom DOM implementation is not yet ready. So in angular 2 they found a system to by pass this \(with attributes component name space\) and be able ot switch to full phantom DOM support when ready.

With this improvement the 3 part of a web components - css, html and js - are packagable in a convenient way. Component by component and without needing to include a full library where 80% of elements are not useful for you.

## Binding

* the syntax has changed
* the 2 way bindings is no more the default
* Top &gt; bottom binding is the default : the binding propagate to component and sub-components
* To make bottom &gt; top updates, you need to use a event system 

## Observable on top of promise

Observable are a new type of async object, like promise but with much more possibilities. The doc of observables is available here : [reactivex.io](http://www.reactivex.io).

Practically at first it could be as simple as replacing the **then** of promises by the **subscribe** of observable. But as you get more familiar with observables, you can do more.

## Debugging

The debug tools are not the same. I've not finished to discovered the possibilities. But I've found a chrome extension [Augury](https://augury.angular.io) that seem the defacto standard for viewing components hierarchy and properties. It display very nicely the dependencies, the components nesting.

Though it does not always display all the public properties of the components classes. It is possible to type $a to debug in the console the component available properties. Though I did not find yet the equivalent of $scope.mydata in angular 1 : a quick way to output available data directly from the element tab of chrome debugger;

It seems that is is not more necessary to write $log.debug as the standard console.log seems enough. How to prevent console logs to display in prod? Do not know yet.

## Zone.js

### Events


---
published: true
layout: post
title: The tutorials I've read to learn Angular 2-4
---

# Angular tutorial selection

Here is a curated list of some good tutorials we used to learn the version 2 of angular.

### Web components

* [https://www.sitepen.com/blog/2017/09/14/using-web-components-with-angular](https://www.sitepen.com/blog/2017/09/14/using-web-components-with-angular)

  How to integrate web components in angular

## General

* Official angular 2 tutorial      

  [https://angular.io/docs/ts/latest/tutorial/](https://angular.io/docs/ts/latest/tutorial/)

* Light weight documentation with both ES6 and Angular 2 made by Ionic team     

  [Learn angular 2](http://learnangular2.com)

* 132+ Video tutorial on specific pratical cases

  [https://egghead.io/technologies/angular2](https://egghead.io/technologies/angular2)

* nicely focused tutorials on a medium hoste dev site [https://netbasal.com/tagged/angular2](https://netbasal.com/tagged/angular2)
* Very well done and free tutorial on angular [https://codecraft.tv/courses/angular](https://codecraft.tv/courses/angular) The good aspect is that the tutorials have both a video a a detailed instruction. And that all the learnings are well size to be progressive.

### Data binding

* Custom text area, input... data binding

[http://lishman.io/angular-2-input-binding](http://lishman.io/angular-2-input-binding)

## Forms

* Guide to forms in angular 2 [http://blog.ng-book.com/the-ultimate-guide-to-forms-in-angular-2/](http://blog.ng-book.com/the-ultimate-guide-to-forms-in-angular-2/)
* Angular forms beyond the basics [http://restlet.com/blog/2016/02/17/implementing-angular2-forms-beyond-basics-part-2/](http://restlet.com/blog/2016/02/17/implementing-angular2-forms-beyond-basics-part-2/) Some more advanced form topics like automatically adding class for bootstrap or async validation...
* Edit forms value programatically : setValue and patchValue

[https://toddmotto.com/angular-2-form-controls-patch-value-set-value](https://toddmotto.com/angular-2-form-controls-patch-value-set-value)

### Reactive forms or model driven fields

* Using Angular2 model driven forms    

  [https://scotch.io/tutorials/using-angular-2s-model-driven-forms-with-formgroup-and-formcontrol](https://scotch.io/tutorials/using-angular-2s-model-driven-forms-with-formgroup-and-formcontrol)

* Introduction to Angular 2 Forms - Template Driven vs Model Driven or Reactive Forms   

  [http://blog.angular-university.io/introduction-to-angular-2-forms-template-driven-vs-model-driven](http://blog.angular-university.io/introduction-to-angular-2-forms-template-driven-vs-model-driven)

* Reactive forms    

  [https://toddmotto.com/angular-2-forms-reactive](https://toddmotto.com/angular-2-forms-reactive)

### Forms fields

* Example of different types of fields    

  [https://scotch.io/tutorials/how-to-deal-with-different-form-controls-in-angular-2](https://scotch.io/tutorials/how-to-deal-with-different-form-controls-in-angular-2)

## Events / Change detection

* Event and @output decorator     

  [https://toddmotto.com/component-events-event-emitter-output-angular-2](https://toddmotto.com/component-events-event-emitter-output-angular-2)

* Change detection in Angular 2

  [http://blog.thoughtram.io/angular/2016/02/22/angular-2-change-detection-explained.html](http://blog.thoughtram.io/angular/2016/02/22/angular-2-change-detection-explained.html)

* How to replicate $scope.$emit with global events ? More technics that official ways

  [http://stackoverflow.com/questions/34700438/global-events-in-angular-2](http://stackoverflow.com/questions/34700438/global-events-in-angular-2)

## Components

* Children view    

  [http://blog.mgechev.com/2016/01/23/angular2-viewchildren-contentchildren-difference-viewproviders](2016-12-15-recommanded-tutorial-for-angular2.md)

* Dump / Smart component architecture :

  A way to organize component to differentiate presentational component highly reusable and intelligent component that actually handle the logic and specific stuff

  [https://teropa.info/blog/2016/02/22/dumb-components-and-visual-feedback-in-angular-apps.html](2016-12-15-recommanded-tutorial-for-angular2.md)

### viewChildren

* [View children, view child and query list](https://netbasal.com/understanding-viewchildren-contentchildren-and-querylist-in-angular-896b0c689f6e) 

### Components @input

* How to define a inner child component property on-change to allow pass observable as input. [http://almerosteyn.com/2016/03/immutable-component-input-from-observable](http://almerosteyn.com/2016/03/immutable-component-input-from-observable)

### Component ngInit vs constructor

* Difference between constructor and ngOnInit     

  [http://stackoverflow.com/questions/35763730/difference-between-constructor-and-ngoninit](http://stackoverflow.com/questions/35763730/difference-between-constructor-and-ngoninit)

### Dynamic components

* [Dynamically creating component in angular 2](http://blog.rangle.io/dynamically-creating-components-with-angular-2/)
* [Another dynamic component creation tutorial](https://netbasal.com/dynamically-creating-components-with-angular-a7346f4a982d)

### Communication between components

* Component inheritance introduced in 2.3 [https://scotch.io/tutorials/component-inheritance-in-angular-2](https://scotch.io/tutorials/component-inheritance-in-angular-2)
* Different ways for communication between components :
  * With input with a setter
  * With input via ngChanges detection
  * With @viewchild that allow to manipulate child methods
  * With a service and observable subject
* [https://angular.io/docs/ts/latest/cookbook/component-communication.html](https://angular.io/docs/ts/latest/cookbook/component-communication.html)
* [Access child DOM and methods @viewChild and template variable](https://alligator.io/angular/viewchild-access-component/)

### Ng-template, ng-container, ng-template-outlet

* [ng-template](https://blog.angular-university.io/angular-ng-template-ng-container-ngtemplateoutlet/)

### DOM

* How to use the angular 2 renderer service to manipulate the DOM in a way all platforms \(server, browser, mobile.. can accept\)

[https://netbasal.com/angular-2-explore-the-renderer-service-e43ef673b26c\#.mah8emsrl](https://netbasal.com/angular-2-explore-the-renderer-service-e43ef673b26c#.mah8emsrl)

* How to use window like with the good old $window angular 1

In this tuto, you learn how to do a wrapper of window to inject in with DI only if usable \(in the browser\)

[https://juristr.com/blog/2016/09/ng2-get-window-ref/](https://juristr.com/blog/2016/09/ng2-get-window-ref/)

## Directives

* Structural \(ngIf...or custom\) or attributes \(ngClass... or custom\) directives      

  [https://angular-2-training-book.rangle.io/handout/advanced-angular/directives/](https://angular-2-training-book.rangle.io/handout/advanced-angular/directives/)

* **ng-show / ng-hide in angular 2** : the angular 2 solution is to bind to hidden prop but there is some issue so read  this article to decide which practice to use

[http://www.talkingdotnet.com/dont-use-hidden-attribute-angularjs-2](http://www.talkingdotnet.com/dont-use-hidden-attribute-angularjs-2/)

## Observables / RxJS

Angular 2 adopted this new concept of observable which basically is a more advanced form of promise. RxJs is the implementation of Observable used by angular which is being developed by Microsoft.

* This post list 3 common problems with can have with observable.
* **Pitfall 1** : not subscribing to an observable is similar to having a function but not exucuting it

> An observable itself is just a definition of a way to handle a stream of values. We can think of it as something close to a function. Creating an observable is somewhat similar to declaring a function, the function itself is just a declaration. Calling the function is something entirely different, as defining a function does not execute its code.
>
> We need to call the function in order for something to happen, and that is also the case with an Observable: we need to subscribe to it in order for it to work!

[http://blog.angular-university.io/angular-2-rxjs-common-pitfalls/](http://blog.angular-university.io/angular-2-rxjs-common-pitfalls/)

* Building a data store with observable [http://blog.angular-university.io/how-to-build-angular2-apps-using-rxjs-observable-data-services-pitfalls-to-avoid/](http://blog.angular-university.io/how-to-build-angular2-apps-using-rxjs-observable-data-services-pitfalls-to-avoid/)
* The Doc of observables transform operator [http://reactivex.io/documentation/operators.html\#transforming](http://reactivex.io/documentation/operators.html#transforming)

## ngFor, ngIf, ...

* Revision of what ngFor can do

  * how to get the index
  * how to track by another value that default \(by object Identity\)
  * using odd, even, last, first for dynamic class naming

  > ngFor by default tracks list items using object identity. This means that if you build a list of new objects from scratch with the exact same values as the previous list and pass this newly built list to ngFor, Angular will not be able to tell that a given list item is already present or not.

[http://blog.angular-university.io/angular-2-ngfor/](http://blog.angular-university.io/angular-2-ngfor/)

* [ng-template and odd, even, last variable in ngFor](https://toddmotto.com/angular-ngfor-template-element#accessing-first-last-odd-even)

### Redux inspired rxjs store

* [https://blog.angular-university.io/angular-ngrx-store-and-effects-crash-course](https://blog.angular-university.io/angular-ngrx-store-and-effects-crash-course) Good introduction to the reactive architecture

## Modules

Organize your code in a modular way. Import a module instead of importing a dozen of files \(javascript modules\). Despite of the use of ES6 modules in angular, angular modules @ngModules are still useful to bundle a feature or a shared utility together.

* [https://scotch.io/bar-talk/getting-to-know-angular-2s-module-ngmodule](https://scotch.io/bar-talk/getting-to-know-angular-2s-module-ngmodule)
* The ng module FAQ is a good place to better understand the ngModules API fine tuning [https://angular.io/docs/ts/latest/cookbook/ngmodule-faq.html\#!\#q-declarable](https://angular.io/docs/ts/latest/cookbook/ngmodule-faq.html#!#q-declarable)
* [https://medium.com/@cyrilletuzi/understanding-angular-modules-ngmodule-and-their-scopes-81e4ed6f7407](https://medium.com/@cyrilletuzi/understanding-angular-modules-ngmodule-and-their-scopes-81e4ed6f7407)
* The angular university tutorial on ngModule

[http://blog.angular-university.io/angular2-ngmodule/](http://blog.angular-university.io/angular2-ngmodule/)

* the official style guide module section

[https://angular.io/styleguide\#!\#application-structure-and-angular-modules](https://angular.io/styleguide#!#application-structure-and-angular-modules)

### components  styling css

* [https://angular.io/docs/ts/latest/guide/component-styles.html\#!\#special-selectors](https://angular.io/docs/ts/latest/guide/component-styles.html#!#special-selectors)
* [http://blog.ng-book.com/css-isolation-in-angular-2-components/](http://blog.ng-book.com/css-isolation-in-angular-2-components/)
* Clear and recent article on module and their differen types

  [https://medium.com/@michelestieven/organizing-angular-applications-f0510761d65a](https://medium.com/@michelestieven/organizing-angular-applications-f0510761d65a)

## Decorator / Annotation syntax \[Typescript\]

* Difference between decorator and annotation [http://blog.thoughtram.io/angular/2015/05/03/the-difference-between-annotations-and-decorators.html](http://blog.thoughtram.io/angular/2015/05/03/the-difference-between-annotations-and-decorators.html)

## Dependency injection

* How to inject window in a service to keep it compatible with angular  dependency injection philosophy        [https://juristr.com/blog/2016/09/ng2-get-window-ref](https://juristr.com/blog/2016/09/ng2-get-window-ref/)

## Pipes

* Simple tutorial to do a custom pipe available in its components then make it available application wide [https://scotch.io/tutorials/create-a-globally-available-custom-pipe-in-angular-2](https://scotch.io/tutorials/create-a-globally-available-custom-pipe-in-angular-2)
* [Angular date pipe tutorial](https://loiane.com/2017/08/angular-tips-formatting-dates-with-a-custom-date-pipe-dd-mm-yyyy/)

## Router

* In depth practical article on the new angular 2 router [https://scotch.io/tutorials/routing-angular-2-single-page-apps-with-the-component-router](https://scotch.io/tutorials/routing-angular-2-single-page-apps-with-the-component-router)
* How to use guards to prevent access to some pages [http://www.sparkbit.pl/angular-2-route-guards-real-life-example/](http://www.sparkbit.pl/angular-2-route-guards-real-life-example/)
* Named router oulet \(same as UI router\) [http://onehungrymind.com/named-router-outlets-in-angular-2/](http://onehungrymind.com/named-router-outlets-in-angular-2/)
* An interceptor for angular 4 [https://medium.com/@amcdnl/the-new-http-client-in-angular-4-3-754bd3ff83a8](https://medium.com/@amcdnl/the-new-http-client-in-angular-4-3-754bd3ff83a8) Mains changes : interceptor, json as a default reponse
* [Other article about new router and interceptor](https://medium.com/@ryanchenkie_40935/angular-authentication-using-the-http-client-and-http-interceptors-2f9d1540eb8)
* [a last article that talk about multiple interceptors](https://alligator.io/angular/httpclient-interceptors/)
* [Router events](https://toddmotto.com/dynamic-page-titles-angular-2-router-events) Events that trigger at route change start, end...

## ES 6

* Exploring JS / Full online book on javascripting with extensive doc on ES6

  [http://exploringjs.com/es6/ch\_destructuring.html\#\_object-destructuring](http://exploringjs.com/es6/ch_destructuring.html#_object-destructuring)

## Typescript

* Detailed explanation about how the modules resolution works for the typescript compiler. How typescript find a module when we write something like :   

  ```javascript
  // Relative import
  import { Component, Input }   from '@angular/core';
  // Non relative  import
  import { OptionService }      from '../../../services/api/option.service';
  ```

[https://www.typescriptlang.org/docs/handbook/module-resolution.html](https://www.typescriptlang.org/docs/handbook/module-resolution.html)

## System.js / JSPM

* A installation guide using JSPM / Typescript and System.js    

  [http://www.mario-brendel.com/angular2-setup/2016/01/28/Angular2\_Jspm\_Setup\_Part1/](http://www.mario-brendel.com/angular2-setup/2016/01/28/Angular2_Jspm_Setup_Part1/)

## Angular 2 & firebase

* Detailed post that explained the principle of firebase, why it is a good solution for BaaS application and allow to develop faster. Then it describe the integration in Angular2 with the angular fire library [http://blog.angular-university.io/angular-2-firebase](http://blog.angular-university.io/angular-2-firebase/)
* The official docs ? [https://angularfire2.com/api/](https://angularfire2.com/api/)
* The doc in the project [https://github.com/angular/angularfire2/tree/master/docs](https://github.com/angular/angularfire2/tree/master/docs)

## AOT Ahead of Time Compilation

* Demystifying AOT : Nice slides that present AOT as an easy thing ... [http://slides.com/wassimchegham/demystifying-ahead-of-time-compilation-in-angular-2-aot-jit\#/30](http://slides.com/wassimchegham/demystifying-ahead-of-time-compilation-in-angular-2-aot-jit#/30)

### Integration of external library / Jquery

* [Wrap any jQuery plugin with Angular 2 component — case study.](https://hackernoon.com/wrap-any-jquery-plugin-with-angular-2-component-case-study-8b00eacec998)
* [USe jquery inside your angular 2-4 component](http://deanmalone.net/post/using-jquery-from-angular2/)

### Angular CLI

* The ultimate guide of angular CLI

[https://www.sitepoint.com/ultimate-angular-cli-reference/](https://www.sitepoint.com/ultimate-angular-cli-reference/)

### New release

* What is new in angular 4

  [http://blog.ninja-squad.com/2017/03/24/what-is-new-angular-4](http://blog.ninja-squad.com/2017/03/24/what-is-new-angular-4/)

### Stripe integration

* a bit old but clear [http://blog.mgechev.com/2016/07/05/using-stripe-payment-with-angular-2/](http://blog.mgechev.com/2016/07/05/using-stripe-payment-with-angular-2/)

### Commits, git....

* Automatical changelogs 

  \[[https://github.com/conventional-changelog/standard-version\]\(https://github.com/conventional-changelog/standard-version](https://github.com/conventional-changelog/standard-version]%28https://github.com/conventional-changelog/standard-version)

  \)

* Conventional commits a standard for commits [https://conventionalcommits.org/](https://conventionalcommits.org/)

### Tests

* [automated test with angular 2](http://www.gistia.com/guide-end-end-testing-angular-2) 

### Webpack build

* [Importing css with webpack angular starter](https://stackoverflow.com/questions/40071845/how-to-import-css-from-node-modules-in-webpack-angular2-app)

### Zones & ngZone

* [runing something outside angular zone so that we skip angular change detection](https://blog.thoughtram.io/angular/2017/02/21)using-zones-in-angular-for-better-performance.html\)

### Progressive web app

* [Progressive web app](https://houssein.me/progressive-angular-applications)

### Responsive

* [Responsive directive to display / hide and more](https://github.com/ManuCutillas/ng2-responsive)

### Theming

* [The more detailed article on how /deep/ ::ng-deep, :host or :host-context works](https://www.concretepage.com/angular-2/angular-2-4-component-styles-host-host-context-deep-selector-example)
* [https://medium.com/@tomastrajan/the-complete-guide-to-angular-material-themes-4d165a9d24d1](https://medium.com/@tomastrajan)

 Allow to use angular material theming abstraction \(you do not need to use other aspect of material if you do not want\). Though it complicate a bit the scss handling, it is a great enhancement for let's say use case where you want to customize your app for your clients, or allow the user to change it's profile visual aspect. Angular material have an opinated but intelligent way of handling colors, that is portable is different environment : mobile, desktop....

### Error handler

* Example of [an interceptor to server as an error handler with then new router - juil 2017](https://medium.com/@amcdnl/the-new-http-client-in-angular-4-3-754bd3ff83a8) For exemple it intercept and d things when request have a status code of let's say 403
  * Global error handler [https://medium.com/@amcdnl/global-error-handling-with-angular2-6b992bdfb59c](https://medium.com/@amcdnl/global-error-handling-with-angular2-6b992bdfb59c)
  * Error handler by extending a [https://hackernoon.com/global-http-request-error-catching-in-angular-486a319f59ab](https://hackernoon.com/global-http-request-error-catching-in-angular-486a319f59ab)


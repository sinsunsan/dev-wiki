---
layout: post
title: Unit test angular 5 with karma + jasmine
published: true
---

### Tutorials on testing

- The best tutorials suite (video + code) on Angular testing
  https://codecraft.tv/courses/angular/unit-testin

- Rangle.io very clear book on angular included testing
  https://angular-2-training-book.rangle.io/handout/testing

- Official document in angular site
  https://angular.io/guide/testing#testing-utility-apis

- Practical tutorial in the context of angular
  https://semaphoreci.com/community/tutorials/testing-components-in-angular-2-with-jasmine

- What is unit test and continuous integration
  http://taco.visualstudio.com/en-us/docs/unit-test-01-primer

- unit testing angular (Jasmine + Karma)
  https://codecraft.tv/courses/angular/unit-testing/jasmine-and-karma/

- A bit old but great description of 3 types of tests to angular components by Victor Savkin
  https://vsavkin.com/three-ways-to-test-angular-2-components-dcea8e90bd8d

- Angular testing recipes

A repository to an app with many testing case ordered by type
https://github.com/juristr/angular-testing-recipes

- Angular testing guide : good practicle documentation of test per types (component, service, pipes....)
  https://medium.com/google-developer-experts/angular-2-testing-guide-a485b6cb1ef0

In this article he explain 3 types of components testing :

- **isolated tests** are a great way to test drive your components and test complex logic.
- **Shallow tests** are isolated tests on steroids, and they should be used when writing a meaningful test requires to render a component’s template.
- **Integration tests** verify that a group of components and services (e.g., the router) work together.

- Testing component by rangle.io
  https://angular-2-training-book.rangle.io/handout/testing/components/

### DebugElement vs fixture.debugElement

- 2 Ways to access the DOM inside unit test in angular

https://stackoverflow.com/questions/37705599/angular2-testing-whats-the-difference-between-a-debugelement-and-a-nativeeleme

https://angular.io/guide/testing#debugelement

- The code Of Debug element a wrapper on DOM API
  https://angular.io/api/core/DebugElement

### Asynchronous problems

- A question on tick and whenStable / How to deal with async data
  https://stackoverflow.com/questions/48328292/unit-testing-value-of-observable-returned-from-service-using-async-pipe

- More about async
  http://devblog.ztp.pt/testing-observables-values-when-using-angular-fakeasync/

- About using async and zone.js
  https://blog.nrwl.io/controlling-time-with-zone-js-and-fakeasync-f0002dfbf48c

- Difference between async and test async
  https://github.com/juristr/angular-testing-recipes/blob/master/src/app/services/async.service.spec.ts

- testing async as if there were not
  https://itnext.io/a-quick-tip-on-testing-observables-e2fbdebef4c

- guide sur les tests asynchrones en francais
  https://guide-angular.wishtack.io/angular/testing/unit-testing/unit-test-asynchrone

### Mocking dependencies

- Good tutorial on the various strategy of mock....
  https://www.ng-conf.org/mocking-dependencies-angular/

### Testing services

- Testing services with HttpTestingController
  https://medium.com/netscape/testing-with-the-angular-httpclient-api-648203820712

- Testing service with https://www.techiediaries.com/angular-testing-httptestingcontroller

### Overriding component : Testing component with child component

http://mylifeandcode.blogspot.fr/2017/03/how-to-mock-out-child-components-in.html

- The same technic as explained in the angular test guide official
  https://angular.io/guide/testing#nested-component-tests

- Overide component in rangle.io tuto
  https://angular-2-training-book.rangle.io/handout/testing/components/overriding.html

### Testing ngrx

- Rangle.io version
  https://angular-2-training-book.rangle.io/handout/testing/redux/

- Todd motto ultimate angular
  https://platform.ultimateangular.com/courses/ngrx-store-effects/lectures/3923987

- Todd motto ultimate angular branch with test
  https://github.com/UltimateAngular/ngrx-store-effects-app/tree/27-testing-effects

### Debugging test

- Console.log
- open a chrome debugger in the karma launched chrome window a trick is that the error messages are something difficult to understand because of the fact that it refere to compile code transformed in ES5 like
  `at Object.reducer (webpack:///./src/app/platform/applicability/store/reducers/applicability.reducer.ts?:104:73)`

so

- by opening the chrome debugger
- going to

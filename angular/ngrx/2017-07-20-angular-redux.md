---
layout: post
title: Angular + Redux = NGRX / A  rxjs powered redux store
published: true
---

# 2017-07-20-angular-redux

![](https://github.com/sinsunsan/dev-wiki/tree/e91a89337cb472fad5198a7110a0eaa8d63d66f5/images/ngrx-diagram.png)

## What it is?

Redux is a way to store in a centralized place data so that all the app can udpate flowlessly by subscribing to some events. For exemple if a component need to listen udpates of "projects" content, he get informed when this event occur.

## Links to start with

* Angular 2 and Redux simplified [https://medium.com/beautiful-angular/angular-2-with-redux-using-ngrx-store-2f93a8ad0dd](https://medium.com/beautiful-angular/angular-2-with-redux-using-ngrx-store-2f93a8ad0dd)
* There is a official [demo / starter app](https://github.com/ngrx/platform/tree/master/example-app) to get a global view on a ngrx based application
* Other [Demo app of angular + redux](https://github.com/ivanderbu2/angular-redux) on how he setup Redux in an angular 2/4 project.
* [Tuto about ngrx for angular 2-4 by angular university why use it + a concrete example](https://blog.angular-university.io/angular-ngrx-store-and-effects-crash-course)
* [heavily commented main reducer of ngrx demo app](https://github.com/ngrx/example-app/blob/master/src/app/reducers/index.ts)
* [UI state managment with Redux in angular 4](https://www.pluralsight.com/guides/front-end-javascript/ui-state-management-with-redux-in-angular-4) in this tuto Hristo Georgiev explain how to use redux in the context of angular 4 to control not only data but also UI like window resizing, hide/display of element.
* [Setting up ngrx](http://www.wisdomofjim.com/blog/setting-up-ngrx-in-an-angular-2-project)
* [Comprehensive Introduction to @ngrx/store ](https://gist.github.com/btroncone/a6e4347326749f938510) A gist with detailed information to learn ngrx store an understand the difference with more classical way of doing it. very detailed with clear code examples.
* [https://kimsereyblog.blogspot.fr/2017/07/managing-global-state-with-ngrx-store.html](https://kimsereyblog.blogspot.fr/2017/07/managing-global-state-with-ngrx-store.html) Step by step exmaple of uses of the main ngrx concepts \(store, reducer, selector...\)

## NGRX Selector

Selectors allow you to select part of the state to display it in component

* [Understanding ngrx selector](http://www.wisdomofjim.com/blog/understanding-ngrx-selectors)
* [More in depth article on what is a selector](https://toddmotto.com/ngrx-store-understanding-state-selectors)

## Go further / More specific articles

* Errors not to be done with  NGRX 

  [http://brianflove.com/2017/11/01/ngrx-anti-patterns](http://brianflove.com/2017/11/01/ngrx-anti-patterns)

* [understanding the \[\] for ngrx action type](http://www.wisdomofjim.com/blog/understanding-the-__-___-___-syntax-for-ngrx-action-types)
* [Get state in effects](https://medium.com/@viestursv/how-to-get-store-state-in-ngrx-effect-fab9e9c8f087)
* [Library of ngrx pattern by Victor Savkin](https://blog.nrwl.io/ngrx-patterns-and-techniques-f46126e2b1e5)

## Reading blog university tutorial notes

* The tuto start with a description of the facebook counter bug that initiated the switch to a redux like architecture for Facebook homepage.
* Notion of viewModel which is the derivation of the a model for the diplay purpose of a view.
* > The transformation from view to view Model is done via a function called a Selector - the input of a Selector is the Model, and the output is the View Model
* the data is stored as a map rather that an array \(optimized for by id query \(same way firebase used\)\)

Example map

* In the store we store both application model and ui state and user preference...

## What to install

* [store](https://github.com/ngrx/store) The main component \(but not obligatory\) to install the architecture. For example you can use actions and effects without to the store

![redux store architecture](https://github.com/sinsunsan/dev-wiki/tree/e91a89337cb472fad5198a7110a0eaa8d63d66f5/images/ngrx-store.png)

* [store dev tools](https://github.com/ngrx/store-devtools) Tools integrated with the chrome extension to debug ngrx powered application
* [router store](https://github.com/ngrx/router-store-builds) integration with the angular router
* [effects](https://github.com/ngrx/effects) Side effects.... \(there is a different version for angular 2 and 4\)

But since 4 version all those packages are put in [one github repository](https://github.com/ngrx/platform). Installing each libs separetely is though still needed.

```text
npm install @ngrx/store @ngrx/store-devtools @ngrx/router-store-builds @ngrx/effects --save
```

Trigger an error is state is not correctly cloned in the reducer

```text
npm install ngrx-store-freeze --save-dev
```

you should then have in your package.json something like

## NGRX terminology

![](https://github.com/sinsunsan/dev-wiki/tree/e91a89337cb472fad5198a7110a0eaa8d63d66f5/images/ngrx-workflow.png)

* **store**: the shared service managed by the ngrx library that manage state and trigger event when the state is changed

**Store** could be thought as the database in the store as a database analogy.

* **state**: Global object that store all global values stored in the store. Each feature module add a property to the store to make available the useful part of the global state
* **reducer**: main function where is defined the logic : \(could be thought as the database tables\). Pratically the reducer have the role to merge / save the state modification with the state global state. Another [explanation](http://www.wisdomofjim.com/blog/setting-up-ngrx-in-an-angular-2-project) :

  > The reducer is the thing that catches and handles the actions that are dispatched from your smart components \(or from your action reducers\), and it is also the thing that actually resets the state to a new, modified state.

**Reducer** could be thought as the database table in the store as a database analogy.

Reducer are a type of function in programmation, that work on a collection of object and produce a final unique object by running function at each loop turn. A very clear definition and examples are available in this [ngrx tutorial](https://gist.github.com/btroncone/a6e4347326749f938510#whats-a-reducer).

* **selector**: function that in charge to retrieved view model structure that are data as need by the UI. 

Selector could be thought as the query in the store as a database analogy.

[Link to utility functions createSelector or createFeatureSelector](https://github.com/ngrx/platform/blob/master/docs/store/selectors.md)

* **action**: an action triggered by the user like clicking on a button, changing view that impact the global state. Action can be loading of data, for example The data have just finished loading, we trigger an action.

  Pratically the purpose of a .action file is the set the string identifier of an action MY\_AWESOME\_ACTION and set the type of the of the payload of the actions \(passed to the effects\)

* **effect**: a change to do when an action is triggered
* **entity**: 

## Who call the reducer function

Every times an action is triggered can be

* the router action 
* ngrx special action at initialisation

## Ngrx Dev tools

_The raw tab or tree tab allow to navigate in the state values_ ![ngrx dev tools raw tab](https://github.com/sinsunsan/dev-wiki/tree/e91a89337cb472fad5198a7110a0eaa8d63d66f5/images/redux-dev-tools.png)

* reducer the table 
* the store the database as explained [comment of example app book reducer](https://github.com/ngrx/platform/blob/master/example-app/app/books/reducers/books.ts#L86)


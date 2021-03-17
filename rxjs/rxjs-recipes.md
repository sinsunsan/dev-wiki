---
layout: post
title: Observable RXJS practical examples for Angular 2-4
published: true
---

# Observables rxjs recipes

### Unsubscribing to observable in Angular

* [https://blog.codecentric.de/en/2018/01/different-ways-unsubscribing-rxjs-observables-angular/](https://blog.codecentric.de/en/2018/01/different-ways-unsubscribing-rxjs-observables-angular/)
* [https://medium.com/@benlesh/rxjs-dont-unsubscribe-6753ed4fda87](https://medium.com/@benlesh/rxjs-dont-unsubscribe-6753ed4fda87)
* [https://medium.com/angular-in-depth/the-best-way-to-unsubscribe-rxjs-observable-in-the-angular-applications-d8f9aa42f6a0](https://medium.com/angular-in-depth/the-best-way-to-unsubscribe-rxjs-observable-in-the-angular-applications-d8f9aa42f6a0)

## Create a timer with observable

Create a timer that will emit a value every 5000ms.

```text
const timer = Rx.Observable.interval(5000);
```

[js bin example of 2 sources \(2 intervals emitters\) with the second slower](http://jsbin.com/vujekucuxa/1)

## \[Observable\] Observable.combineLatest

* **When to use?** : You have 2 queries or more. You need to do something depending on of the results of those queries. For example, you need to wait for page params and get the connected user information...

> CombineLatest emits an item whenever any of the source Observables emits an item \(so long as each of the source Observables has emitted at least one item\)

So you have 2 or more async observables, the Observable.combineLatest is called after each emitted their first value, and give the opportunity to a function to remit a item with the value of the last emitted item

* [official doc](http://reactivex.io/documentation/operators/combinelatest.html)

## \[Subject\] Behavior subject

A variable that is changed using next\(\) and "watched" using subscribe

* [official doc on subjects](http://reactivex.io/documentation/subject.html)
* A good comparison of **behaviorSubject** **ReplaySubject** and **asyncSubject** [https://medium.com/@luukgruijs/understanding-rxjs-behaviorsubject-replaysubject-and-asyncsubject-8cc061f1cfc0](https://medium.com/@luukgruijs/understanding-rxjs-behaviorsubject-replaysubject-and-asyncsubject-8cc061f1cfc0)
* **When to use?** : When we need to keep an updatable value \(for example the connected user\) and get all components updated when this value change

## \[Operator\] map

`import 'rxjs/add/operator/map';`

Allow to change the value of each emitted items before it is sent to function subscribing to it.

* **When to use?** : After API query when we generally want to convert to JSON, control with libraries like [TypedJson](https://github.com/JohnWeisz/TypedJSON)...
* [ official doc on map operator](http://reactivex.io/documentation/operators/map.html)

## \[Operator\] flatmap

* [Difference between map & flapmap](https://namitamalik.github.io/Map-vs-FlatMap/)

Mind that in JS the name is not flatmap ! Look at [flatmap official doc](http://reactivex.io/documentation/operators/)flatmap.html

## \[Operator\] do

`import 'rxjs/add/operator/do';`

[Learn RXJS doc on do](https://www.learnrxjs.io/operators/utility/do.html)

* **When to use?** : To perform an action like logging that do not transform the observable result

## \[Operator\] catch

`import 'rxjs/add/operator/catch';`

[Learn RXJS doc on catch](https://www.learnrxjs.io/operators/error_handling/catch.html)

* **When to use?** : to catch error, return an observable with the error information

## \[Operator\] take

`import 'rxjs/add/operator/take';`

* **When to use?** : When you want to limit the number of returned elements. For example take only the 5 first elements of a stream of observable.

  [Learn RXJS doc on take](https://www.learnrxjs.io/operators/filtering/take.html)

## \[Filter\] filter

* **When to use?** : Select the condition to receive a given observable, for example you want to make an API call only if the parameters are available 

[Learn RXJS on filter](https://www.learnrxjs.io/operators/filtering/filter.html)

## \[Operator\] withLatestFrom

`import 'rxjs/add/operator/withLatestFrom';`

* **When to use?** Combine 2 sources with the latest emitted version for the second source. withLatestFrom is generally followed by a map where the 2 sources results `.map([source1, source2) => { //handle 2 sources }` can be manipulated

[Learn RXJS doc on withlatestfrom](https://www.learnrxjs.io/operators/combination/withlatestfrom.html)

## \[Operator\] exhaustMap

* **When to use?**: Map values to inner observable and stop emitting value until inner observable map finish \(=exhaust\)

  ```text
  this.actions$.ofType(Auth.LOGIN)
    .map((action: Auth.Login) => action.payload)
    .withLatestFrom(this.geolocationService.refreshLocation())
    // auth and geo are mapped to inner observable (sub-observable)
    // if new values are emitted but  inner observable are not completed
    // they won't be mapped again
    .exhaustMap(([auth, geo]) => this.authService.login(auth, geo)
        .map(loginAuth => new Auth.LoginSuccess({ auth: loginAuth }))
        .catch(error => of(new Auth.LoginFailure(error)))
    );
  ```

  [Learn RXJS doc on exhaustMap](https://github.com/btroncone/learn-rxjs/blob/master/operators/transformation/exhaustmap.md)

## \[Function\] pipe method

[https://blog.hackages.io/rxjs-5-5-piping-all-the-things-9d469d1b3f44](https://blog.hackages.io/rxjs-5-5-piping-all-the-things-9d469d1b3f44)

Pipe method is available from Rxjs 5.5

### Return an observable when another observable emit a value

```typescript
this.closeEditing$ 
.pipe(switchMap(() => this.lines$))
.subscribe(lines => {
```



{% embed url="https://www.freecodecamp.org/news/understand-rxjs-operators-by-eating-a-pizza/" %}




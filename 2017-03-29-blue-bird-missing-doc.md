---
layout: post
title: Blue bird missing doc / the essential function decrypted
published: true
---


Blue bird is a great library of promise for front end (angular) and backend (node).
But its documentation is definitely not good.
Let's list and explain shorty the difference between each useful functions this library provide.


[Blue bird documentation](http://bluebirdjs.com/)

## Promise Concepts

* Sequential or Parallel processing

**Sequential** processing means each promises is processed one after the other.
Could be useful if you want to have a control on the flow of processing. Or if you need the result of previous promise to process the next.

**Parallel** processing means the promises are processed at the same time. You cannot garanty that the order will be preserved.


## 2 anti pattern not to fall in

* Creating an explicit promise that wrap an already promise
http://bluebirdjs.com/docs/anti-patterns.html#the-explicit-construction-anti-pattern

* http://bluebirdjs.com/docs/anti-patterns.html#the-explicit-construction-anti-pattern
```js
then((success) => { }, error=> { })
```
instead of
```js
then(() => {

})
.catch(() => {

})
```


##  Useful bluebird function

* **Promise.all**
  - Params: Array of promise
  - Process in parallel
  - Reject early if an error occur
  - the return value is an array of each promises return in the order they were define

* **Promise.each**
  Same than promise.all but
  - Process in sequence

* **Promise.join**

It is recommended to use Promise.join instead or Promise.all
when the action to do are fixed  in advance and not numerous.
In this case only 3 promises that we know in advance.

```js
var Promise = require("bluebird");
var join = Promise.join;

join(getPictures(), getComments(), getTweets(),
    function(pictures, comments, tweets) {
    console.log("in total: " + pictures.length + comments.length + tweets.length);
});
```

* [**Promise.some**](http://bluebirdjs.com/docs/api/promise.some.html)

The same that lodash `_.some` but with promises and with the count parameter that allow  to tell the minimal promises that need to be fullfilled before

Example of the doc log only the 2 fastest server to respond.

````js
Promise.some([
    ping("ns1.example.com"),
    ping("ns2.example.com"),
    ping("ns3.example.com"),
    ping("ns4.example.com")
], 2).spread(function(first, second) {
    console.log(first, second);
});
````

* [**Promise.props**](http://bluebirdjs.com/docs/api/promise.props.html)

Use the properties of an object to define promise to be perfomed.
The advantage is that the result is accessible with the same properties name that the input object.
Giving the benefit of the spread() operator (instead of the then())
```js
Promise.props({
    pictures: getPictures(),
    comments: getComments(),
    tweets: getTweets()
}).then(function(result) {
    console.log(result.tweets, result.pictures, result.comments);
});
```

* [**finally()**](http://bluebirdjs.com/docs/api/finally.html)

````js
Promise.all([
  /* Array of promises */

])
.then(() => {
  // To do when all promises array resolve
})
.catch(() => {
  // To do if any of the promise in the array had arrors
})
.finally(() => {
  // To do after the then() or catch() indepedantly of the Promise faith (success or errors)
})
````

* [**cancel()**](http://bluebirdjs.com/docs/api/cancel.html)
  Cancel a promise if it has not been received already

* [**spread()**](http://bluebirdjs.com/docs/api/spread.html)
  The result of promise.all is an array of promises return, but what  if you want to define them as parameters ?

````js
 let arrayOfPromises = [
   promise1,
   promise2
 ];
  Promise.all(arrayOfPromises)
  .spread((returnOfPromise1, returnOfPromise2) =>  {
      console.log("return of promise1 " , returnOfPromise1);
      console.log("return of promise2 " , returnOfPromise1);
  });
  // Instead of
  Promise.all(arrayOfPromises)
  .then((result)  => {
      console.log("return of promise1 " , result[0]);
      console.log("return of promise2 " , result[2]);
  });
````

  * [Global rejection error hook](http://bluebirdjs.com/docs/api/error-management-configuration.html#global-rejection-events)

Allow to do something globally when error occured

````js
  // NOTE: event name is camelCase as per node convention
  process.on("unhandledRejection", function(reason, promise) {
      // See Promise.onPossiblyUnhandledRejection for parameter documentation
  });

  // NOTE: event name is camelCase as per node convention
  process.on("rejectionHandled", function(promise) {
      // See Promise.onUnhandledRejectionHandled for parameter documentation
  });
````

* **[isFullfilled]**(http://bluebirdjs.com/docs/api/isfulfilled.html)

test if the promise is fullfilled

````js
let mypromise = Promise.all()
// More code

timeout(500, () => {
  if (!mypromise.isFulfilled) {
    console.log('still not done')
  }
})
````

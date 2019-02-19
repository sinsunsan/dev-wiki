---
layout: post
title: Javascript recipes
published: true
---

### Get the computed style of an html element

getComputedStyle is a function attach to window object. 
It allow to get the exact same information than the chrome computed properties
So the list of all properties of a given element 

`getComputedStyle($('body'))`

To extract only the info you need you can take advantage of ES6 syntax 
````js
const {
      order,
      height,
    } = getComputedStyle(el)
````
So here we got for example order: 0 and height: 25078.3px

To extract only the numerical value of the pixel and drop the .3
You can use 
````js
parseInt(getComputedStyle($('body')).height, 10)
````
The result is 25078

### What is copying a  object ? 

https://medium.com/@tkssharma/objects-in-javascript-object-assign-deep-copy-64106c9aefab

The original 

https://scotch.io/bar-talk/copying-objects-in-javascript


### Immutability 

* https://hackernoon.com/introducing-immer-immutability-the-easy-way-9d73d8f71cb3
* https://github.com/facebook/immutable-js
* https://github.com/mweststrate/immer
---
layout: post
title: Javascript recipes
published: true
---

# Javascript recipes

### Get the computed style of a html element

getComputedStyle is a function attach to window object. It allows to get the exact same information than the chrome computed properties So the list of all properties of a given element

`getComputedStyle($('body'))`

To extract only the info you need you can take advantage of ES6 syntax

```javascript
const {
      order,
      height,
    } = getComputedStyle(el)
```

So here we got for example order: 0 and height: 25078.3px

To extract only the numerical value of the pixel and drop the .3 You can use

```javascript
parseInt(getComputedStyle($('body')).height, 10)
```

The result is 25078

### What is copying an  object ?

[https://medium.com/@tkssharma/objects-in-javascript-object-assign-deep-copy-64106c9aefab](https://medium.com/@tkssharma/objects-in-javascript-object-assign-deep-copy-64106c9aefab)

The original

[https://scotch.io/bar-talk/copying-objects-in-javascript](https://scotch.io/bar-talk/copying-objects-in-javascript)

### Immutability

* [https://hackernoon.com/introducing-immer-immutability-the-easy-way-9d73d8f71cb3](https://hackernoon.com/introducing-immer-immutability-the-easy-way-9d73d8f71cb3)
* [https://github.com/facebook/immutable-js](https://github.com/facebook/immutable-js)
* [https://github.com/mweststrate/immer](https://github.com/mweststrate/immer)

### False switch case 

{% embed url="https://gist.github.com/sinsunsan/bc176b1d845d5f7dc14d63e946b1278d" %}

### Conditionally insert some properties in an object 

{% embed url="https://medium.com/@mikeh91/conditionally-adding-keys-to-javascript-objects-using-spread-operators-and-short-circuit-evaluation-acf157488ede" %}






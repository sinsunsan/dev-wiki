---
layout: post
title: Javascript and ES6 functions to use as an alternative to lodash
published: true
---

# Alternative to lodash with ES6

Lodash is great, we have an article about [most useful lodash functions](http://dev.sebastienlucas.com/lodash-best-of/). But those functions are pretty low level. They should be at the level of the language itself JavaScript. With ES5 / ES6, JavaScript got more powerful, so it is time to stop using some of lodash function to use their native equivalent. The advantage is that we could more easily tweak the function for our needs which is not possible with lodash. And get more knowledge and confidence about ES6. And also get rid of lodash entirely to have fewer dependencies.

Lodash alternatives are compiled in this repository, please contribute [https://github.com/you-dont-need/You-Dont-Need-Lodash-Underscore](https://github.com/you-dont-need/You-Dont-Need-Lodash-Underscore)

Another article for alternative to lodash [https://www.reindex.io/blog/you-might-not-need-underscore/](https://www.reindex.io/blog/you-might-not-need-underscore/)

And 10 of them are explained in this article [https://www.sitepoint.com/lodash-features-replace-es6/](https://www.sitepoint.com/lodash-features-replace-es6/)

## array.reduce instead of \_.keysBy

Convert array to an object with id as keys

## Object.keys instead of \_.keys

Convert an object with key to an array

## Object.assign or spread operator instead of _.defaults or_ .extends, \_.assign...

Clone an object

## Array.filter instead of \_.filter

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

## Array.find instead of \_.find

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/find](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)

## Union with deduplication

A blog post illustration union, intersection and difference [http://2ality.com/2015/01/es6-set-operations.html](http://2ality.com/2015/01/es6-set-operations.html)

Mind that it works only with array of values, not of objects


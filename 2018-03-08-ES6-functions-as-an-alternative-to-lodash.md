---
layout: post
title: Javascript and ES6 functions to use as an alternative to lodash
published: true
---

Lodash is great, we have an article about [most useful lodash functions](http://dev.sebastienlucas.com/lodash-best-of/). But those functions are pretty low level. They should be at the level of the language itself javascript. With ES5 / ES6, javascript got more powerful, so it is time to stop using some of lodash function to use their native equivalent. The advantage is that we could more easily tweak the function for our needs which is not possible with lodash. And get more knowledge and confidence about ES6. And also get rid of lodash entirely to have less dependencies.

Lodash alternatives are compiled in this repository, please contribute 
https://github.com/you-dont-need/You-Dont-Need-Lodash-Underscore

Another article for alternative to lodash 
https://www.reindex.io/blog/you-might-not-need-underscore/

And 10 of them are explained in this article 
https://www.sitepoint.com/lodash-features-replace-es6/

### array.reduce instead of _.keysBy

Convert array to an object with id as keys

<script src="https://gist.github.com/sinsunsan/4b733d2e03fb77c6bb8cea160fbb8ef7.js"></script>


### Object.keys instead of _.keys

Convert an object with key to an array

<script src="https://gist.github.com/sinsunsan/39c3573696e953fe075c317a77590c5a.js"></script>


### Object.assign or spread operator instead of _.defaults or _.extends, _.assign...

Clone an object 

<script src="https://gist.github.com/sinsunsan/4152a5c0fc6058fd876585792b611c3f.js"></script>

### Array.filter instead of _.filter

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter

### Array.find instead of _.find 

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find


### Union with deduplication 

<script src="https://gist.github.com/sinsunsan/554024c0d09aafd2eb414ad409a2d184"></script>

A blog post illustration union, intersection and difference 
http://2ality.com/2015/01/es6-set-operations.html

Mind that it works only with array of values, not of objects
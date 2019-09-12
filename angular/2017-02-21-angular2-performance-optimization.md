---
layout: post
title: Angular 2 performance optimization
published: true
---

# Perfomance optimization

## Performance improvement checklist

* Performance check list for Angular : [https://github.com/mgechev/angular-performance-checklist\#caching](https://github.com/mgechev/angular-performance-checklist#caching)



## Fixing and detecting memory leaks

* [https://itnext.io/angular-rxjs-detecting-memory-leaks-bdd312a070a0](https://itnext.io/angular-rxjs-detecting-memory-leaks-bdd312a070a0)
* Explanation on how to use chrome dev tools for that and memory related concepts [https://developers.google.com/web/tools/chrome-devtools/memory-problems/](https://developers.google.com/web/tools/chrome-devtools/memory-problems/)

## Enable Prod mode

### What does it do :

* Reduce to a single check the change detection
* do not use deep comparison of object for change detection

[http://stackoverflow.com/questions/34868810/what-is-difference-between-production-and-development-mode-in-angular2](http://stackoverflow.com/questions/34868810/what-is-difference-between-production-and-development-mode-in-angular2)

### How to

```text
import { enableProdMode } from '@angular/core';

// enable prod for faster renders
enableProdMode();
```

## AOT / Ahead of time compilation

Precompilation of the code &gt; Link to article

## Universal angular

Prerendering on the server side.

Look [ at our introduction](http://dev.sebastienlucas.com/universal-angular/) and [step by step starter](http://dev.sebastienlucas.com/how-to-use-the-angular-universal-starter/)

## 


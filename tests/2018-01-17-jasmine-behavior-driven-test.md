---
layout: post
title: Jasmine behavior driven test
published: true
---

# Jasmine test

Very good introduction to Jasmine [https://codecraft.tv/courses/angular/unit-testing/jasmine-and-karma](https://codecraft.tv/courses/angular/unit-testing/jasmine-and-karma)

Video explanation : talk about unit test, what is it, test in general... The jasmine Documentation [https://jasmine.github.io/api/3.0/global.html\#beforeEach](https://jasmine.github.io/api/3.0/global.html#beforeEach)

## JASMINE before / after functions

Run before all test suite tests

* beforeAll 
* afterAll 

Run before each test, before this test or after this test

* beforeEach
* afterEach

## Disable temporarily a test

Put x in front of describe \(the test suite = group of tests\) `xdesribe` and x in front of it \(the test\) so `xit`

It allows to disable a test temporarily though still listing it and not commenting it To be able to see the test code.

Put f in front of it to focus only on one test \(only run one test\) so write `fit('the test to focus on')`

## The hierarchy of unit test

* A test suite : a group of test \(describe\)
* A test spec : one individual test \(it\)
* A test expectation : what we are testing \(expect\)

## What do Karma do

Karma is a test runner, it is not compulsory to use it. Though it is easier :

* It reruns the tests when code change 
* It open a separate browser \(headless\)
* It gets Jasmine result in the command line 

[https://github.com/karma-runner/karma/releases](https://github.com/karma-runner/karma/releases)

## Jasmine Spy

* [https://www.htmlgoodies.com/html5/javascript/spy-on-javascript-methods-using-the-jasmine-testing-framework.html](https://www.htmlgoodies.com/html5/javascript/spy-on-javascript-methods-using-the-jasmine-testing-framework.html)
* Jasmine doc on spies [https://jasmine.github.io/api/3.0/global.html\#spyOn](https://jasmine.github.io/api/3.0/global.html#spyOn)
* Jasmine Spy spreadsheet [http://tobyho.com/2011/12/15/jasmine-spy-cheatsheet/](http://tobyho.com/2011/12/15/jasmine-spy-cheatsheet/)

## Remove code duplication in Jasmine

[https://juristr.com/blog/2014/10/avoid-test-code-duplication-jasmine](https://juristr.com/blog/2014/10/avoid-test-code-duplication-jasmine) Duplication using a way to invoke describe by using a function

[https://gist.github.com/traviskaufman/11131303](https://gist.github.com/traviskaufman/11131303) Git that explain why using **this** in the test context. Some recent comment explained how to use it with typescript as well.

[https://www.reddit.com/r/javascript/comments/60a10r/improve\_your\_javascript\_unit\_testing\_with/](https://www.reddit.com/r/javascript/comments/60a10r/improve_your_javascript_unit_testing_with/) Discussion about how to write units tests with multiple expect in it or not, parameterized tests...

[https://gist.github.com/sinsunsan/cb1779b3b83a33fe8446bf27ef7f6149](https://gist.github.com/sinsunsan/cb1779b3b83a33fe8446bf27ef7f6149) Example of parameterized test in JavaScript

## Debug Jasmine test

* Error due to a missing selector with `debugElement`

```javascript
const myElement = fixture.debugElement.query(By.css(.missing-class));
// myElement.nativeElement will trigger an error
```

`Failed: Uncaught (in promise): TypeError: Cannot read property 'nativeElement' of undefined`

* angular test with data that come from a resolver

[https://stackoverflow.com/questions/42656045/angular2-testing-and-resolved-data-how-to-test-ngoninit](https://stackoverflow.com/questions/42656045/angular2-testing-and-resolved-data-how-to-test-ngoninit)


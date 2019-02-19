---
layout: post
title: Jasmine behavior driven test
published: true
---

Very good introduction to Jasmine https://codecraft.tv/courses/angular/unit-testing/jasmine-and-karma

Video explanation : talk about unit test, what is it, test in general...
The jasmine Documentation https://jasmine.github.io/api/3.0/global.html#beforeEach

### JASMINE before / after functions

Run before all test suite tests

* beforeAll 
* afterAll 

Run before each tests, before this test or after this test

* beforeEach
* afterEach


### Disable temporarly a test 

Put x in front of describe  (the test suite = group of tests) `xdesribe`
and x in front of it (the test) so `xit`

It allows to disable a test temporarly though still listing it and not commenting it 
To be able to see the test code.

put f in front of it to focus only on one test (only run one test)
so write 
`fit('the test to focus on')`


### The hierarchy of unit test 

* A test suite : a group of test (describe)
* A test spec : one individual test (it)
* A test expectation : what we are testing (expect)


### What do Karma do 

Karma is a test runner, it is not compulsary to use it. Though it is easier : 

* It rerun the tests when code change 
* It open a separate browser (headless)
* It get Jasmine result in the command line 

https://github.com/karma-runner/karma/releases

### Jasmine Spy 

* https://www.htmlgoodies.com/html5/javascript/spy-on-javascript-methods-using-the-jasmine-testing-framework.html
* https://jasmine.github.io/api/3.0/global.html#spyOn


### Remove code duplication in Jasmine 

https://juristr.com/blog/2014/10/avoid-test-code-duplication-jasmine
Deplication using a way to invock describe by using a function 

https://gist.github.com/traviskaufman/11131303 Git that explain why using **this** in the test context. 
Some recent comment explained how to use it with typescript also.

https://www.reddit.com/r/javascript/comments/60a10r/improve_your_javascript_unit_testing_with/ Discussion about how to write units tests with multiple expect in it or not, parametrized tests...

https://gist.github.com/sinsunsan/cb1779b3b83a33fe8446bf27ef7f6149
Exemple of parametrized test in javascript 

### Debug Jasmine test 

* Error due to a missing selector with debugElement 

```js
const myElement = fixture.debugElement.query(By.css(.missing-class));
// myElement.nativeElement will trigger an error
```

`Failed: Uncaught (in promise): TypeError: Cannot read property 'nativeElement' of undefined`


* angular test with data that come from a resolver

https://stackoverflow.com/questions/42656045/angular2-testing-and-resolved-data-how-to-test-ngoninit
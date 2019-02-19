---
layout: post
title: End 2 End test with angular protractor
published: true
---

# E2e tests with protactor

Protractor is the main framework in angular to perfom e2e tests. You can find the official documentation here : [http://www.protractortest.org/\#/](http://www.protractortest.org/#/)

To get to know what a end to end test is in pratice for angular. I recommend this small tutorial [https://medium.com/paramsingh-66174/automate-e2e-testing-of-angular-4-apps-with-protractorjs-jasmine-fcf1dd9524d5](https://medium.com/paramsingh-66174/automate-e2e-testing-of-angular-4-apps-with-protractorjs-jasmine-fcf1dd9524d5)

That make you test that an app have a title that it should have

### How to write good e2e test

* [http://www.protractortest.org/\#/style-guide](http://www.protractortest.org/#/style-guide)
* [https://github.com/CarmenPopoviciu/protractor-styleguide](https://github.com/CarmenPopoviciu/protractor-styleguide)

## Get a better display of tests executions

* Display a nicer html version of the tests [https://www.npmjs.com/package/protractor-jasmine2-html-reporter](https://www.npmjs.com/package/protractor-jasmine2-html-reporter)
* Display how to specs are being evaluated in real time [https://github.com/bcaudan/jasmine-spec-reporter](https://github.com/bcaudan/jasmine-spec-reporter)

## Debug tests

* Element not visible [https://stackoverflow.com/questions/37809915/element-not-visible-error-not-able-to-click-an-element](https://stackoverflow.com/questions/37809915/element-not-visible-error-not-able-to-click-an-element)
* browser.sleep\(20000\) give you 20s to inspect manually in the browser that the automated test opened what is going on
* Use **fit** to the test you want to debug or build so that you don't waste time with the others. Just change it\(''\) par fit\(''\) for focus, and when you are done do change it back.


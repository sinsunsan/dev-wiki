---
layout: post
title: Angular 2 forms cheatsheets
published: true
---

# 2016-12-15-angular2-form-cheatsheet

Angular 2 form add many improvements on angular 1 version. There is good in [depth tutorials](http://dev.sebastienlucas.com/good-tutorials-to-learn-angular2/) explaining how to use it.

Let's list the most important elements to record for those who used angular forms in version 1.

## 2 ways to build forms : template driven and model driven

Template driven is the traditional way with html and angular directives.

* **Advantages**:
  * Feel more natural and readable
  * More customizable for use case not foreseen by the framework
* **Disadvantages**:
  * Many boilerplates code : code that is always the same in all forms and not specific to this specific form. Boilerplates code is error prone because you can always mistype... And when there is a change in a big site, hundreds of templates need to be changed.
  * Not testable with units tests \(Only by E2E tests\)

Model driven is with a form javascript API that angular 2 introduces in core. Where as in the version 1 only libraries were developing this concept.

* **Advantages**:
  * Very compact declarative style  form definition
  * Minimal boilerplates
  * Easy updates and config sharing among many forms
  * Testable with units tests
* **Disadvantages**:
  * You need to learn the API
  * May feel less understandable for people that do not know the API

## Template driven forms

* We need to import the form module to enable ngModel and form stuff

```typescript
import {FormsModule} from "@angular/forms";
@NgModule({
    declarations: [App],
    imports: [BrowserModule, FormsModule],
    bootstrap: [App]
})
```

### The Ng-model accept two-way or one-way binding

With angular 1 forms, we had the case that the changes in the form get reflected instantly in the rest of the page. As 2 way binding was the default. This could not be always intended. In angular 2, you have the choice :

* **\[\(ngModel\)\]="proj.field"** : to have the form state reflected back in real time \(two way binding\)
* **\[ngModel\]="proj.field"** : to have the form data just initialized and actualized programmatically when the form is submitted and when the api call is successful. \(one way binding\)
* **ngModel**: If you do not want initialization but form validation a simple  ngModel without any field or object

### Syntax the name the form

To identify the form and be able to access it's data \(not the ng-model\) but all data about form validation, touched, non touched states... you use this syntax :

**\#NameOfYouForm="ngForm"**

Yes it is strange! But why not?

```markup
<form #myForm="ngForm" (ngSubmit)="submit()">
```

You probably need to access it to prevent the form to be submitted. **myForm.valid** is testing a global form bolean that is true if all form fields are valid \(required fields filled, no validation errors...\)

```markup
<button type="submit" [disabled]="!myForm.valid">Submit</button>
```

### Form controls

Each field identified by a name is

```markup
<input type="text" name="project">
```

And could be found in **myForm.forms.controls**.


---
layout: post
title: Angular 2 recipes / Tips and tricks
published: true
description: Some tips and tricks for specific cases in Angular
---

# Angular Recipes

Tips & tricks for tricky but useful things in angular 2. The type of problems that are too small to deserve a full blog post, and that you do not know how to name to search for.

### Elvis operator and bracket notation

Bracket notation is javascript is an alternative to dot notation to display the content of an object. The main advantage is has is that you can use variable inside the bracket to display a property whose name depends of a variable.

Elvis operator is a syntax for angular 2 that allow telling angular renderer to ignore template binding of sub-properties for object that does not exist yet. Indeed, it is generally that the object is not yet loaded from the backend.

From this [link](http://stackoverflow.com/questions/35768768/angular2-using-elvis-operator-on-object-key-with-forward-slash)

The Elvis operator is only available for the . notation, not for other operators like \[\]. As a workaround use

```text
data?.record ? data.record['name/first'] : null
```

### Select an element of the DOM

Well explained [here](http://stackoverflow.com/a/38944920/1453811)

**Use ViewChild with \#localvariable as shown here,**

```markup
<textarea  #someVar  id="tasknote"
                  name="tasknote"
                  [(ngModel)]="taskNote"
                  placeholder="{{ notePlaceholder }}"
                  style="background-color: pink"
                  (blur)="updateNote() ; noteEditMode = false " (click)="noteEditMode = false"> {{ todo.note }}

</textarea>
```

In component,

```javascript
//OLD Way
import {ElementRef} from '@angular/core';

@ViewChild('someVar') el:ElementRef;

ngAfterViewInit()
{
   this.el.nativeElement.focus();

}
```

New API with renderer....

```javascript
//NEW Way
import {ElementRef} from '@angular/core';

    @ViewChild('someVar') el:ElementRef;


constructor(private rd: Renderer) {}

  ngAfterViewInit() {
    this.rd.invokeElementMethod(this.el.nativeElement,'focus');
  }
```

### Prevent error when module are failing to be imported

Module handling in JS is a headache. Sometimes it just don't works. But you still need to use a js lib the old way \(with a script in the index.html\).

You can fool typescript to allow you to use the missing library \(that will exist at run time\).

```javascript
declare var braintree:any;
```

### Object property binding & async pipe with bracket syntax

Yes but how to use a bracket syntax with async syntax.

[http://stackoverflow.com/questions/36803389/angular2-async-pipe-not-does-not-fill-object-data-into-template](http://stackoverflow.com/questions/36803389/angular2-async-pipe-not-does-not-fill-object-data-into-template)

I have an observable that I want to pass to a component. Once passed I want a sub property that is static in that case : the first item of an array. Or may be dynamic, a component property.

The problem is that : `(imagesFB | async)[0]` would fail because the item does not exist at first and the async is for imagesFB not for the resulting array that \(imagesFB \| async\) return.

So with a ternary syntax :

```text
 (bolean) ? /* code if true */ : /* code if false */ ;`
```

We do the trick.

```text
ui-gallery-image([image]="(imagesFB | async) ? (imagesFB | async)[0] : null")
```

### Instantiating a class or static method

There are 3 keywords that can be used in a class. To defined a property or method

* **public** to get the method available from other classes
* **private** to get it only usable inside the class
* **static** allow to use a class without instantiating it

  Instantiate a class, is creating a local copy of it. For example if we are in a component, that mean that we are using an instance of a class.

  An instance is creating by passing it to the component constructor like this.

```javascript
import { UploadService }         from '../../../services/api/upload.service'

export class UiUploadUploadcareComponent {
  constructor(
    private uploadService: UploadService,
  ){
  }

  upload() {
    // we use the instance of the class with this
    this.uploadService.upload()
  }
```

But by using static we do not need, and we cannot actually create a local instance

```javascript
import { StaticService }         from '../../../services/static.service'

export class UiUploadUploadcareComponent {
  constructor(
    // we do not need to instanciate the class
  ){
  }

  upload() {
    // we use the static method useStaticClass
    // of StaticService  class without the this keyword
    StaticService.useStaticClass()
  }
```

### Simplify module definition with the spread operator

* [Doc of spread operator](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Operators/Spread_operator)

```javascript
@NgModule({
  imports: [
    ...MODULES
  ],
  declarations: [
    ...PIPES,
    ...COMPONENTS
  ],
  exports: [
    ...MODULES,
    ...PIPES,
    ...COMPONENTS
  ]
})
```

### Export of modules to be compatible with lazy loading, AOT and universal angular

```javascript
const PIPES = [
  // put pipes here
];

const COMPONENTS = [
  // put shared components here
];

const PROVIDERS = [
  ModelService,
  ApiService
]

@NgModule({
  imports: [
    ...MODULES
  ],
  declarations: [
    ...PIPES,
    ...COMPONENTS
  ],
  exports: [
    ...MODULES,
    ...PIPES,
    ...COMPONENTS
  ]
})
export class SharedModule {
  static forRoot(): ModuleWithProviders {
    return {
      ngModule: SharedModule,
      providers: [
        ...PROVIDERS
      ]
    };
  }
}
```

### Navigate to a defined page in the component or service

```javascript
import { ActivatedRoute, Router }           from '@angular/router';

// Component definition

constructor(
    private router: Router,
    private route: ActivatedRoute,
  ) {}

// Inside a component method

this.router.navigate([], { queryParams: {step : this.order.step}, relativeTo: this.route });
```

### Do somethings after 2 or more promises resolve

Usage of Rxjs Observable.combineLatest to do something and combine the results of the 2 or more promises resolved.

```javascript
import { Observable } from 'rxjs'

Observable.combineLatest(
      this.translationService.getTranslation("reset_title"),
      this.translationService.getTranslation("reset_desc")
    )
    .subscribe(results => {
      // DO something
    })
```

### Redirect to the same path but changing one query params

The trick is \[\] to tell same page.

```javascript
this.router.navigate([], { relativeTo: this.route, queryParams: { step: this.steps[0] } });
```

### Redirect to the same path changing only the last path parameter

The trick is to use relative path syntax of angular 2 router

```javascript
// change orderId only while we are at order/22 for example
// but keeping all parameters
this.router.navigate(['../', this.order._id], { queryParams: this.params, relativeTo: this.route });

// For this  path (defined in routing configuration)
{ path: 'order/:orderId', component: SROrderPage },
```

### watching queryparams and params changes

* **queryparams**  are optional `?step=2&lang=fr` so step and lang
* **params** are in the path `/project/:projectId` so project Id in that cas

For both we use the Activated route service, so we place in our constructor

```javascript
constructor(
    private route: ActivatedRoute) {}
```

then we set a watcher in our ngInit\(\)

```javascript
ngOnInit() {
      this.route
      .params
      .subscribe(routeParams => {
        // trigger when route params change
        // routeParams = { projectId: 22 }
      });

      this.route
      .queryParams
      .subscribe(queryParams => {
        // trigger when route params change
        // project/22?lang=fr
        // queryParams = { lang: 'fr '}
      });

  }
```

For query params read this [good tuto](https://angular-2-training-book.rangle.io/handout/routing/query_params.html) for more info

### Execute a js library outside of the scope of angular

Angular run inside an execution context so is not accessible in the global scope of the page. But some libraries like jQuery exist in the global scope of the page.

So here is an example on [how to run a jquery library from an angular component](https://github.com/devmark/ngx-slick/blob/master/src/slick.component.ts).

Import of the NgZone module

```javascript
import {
    Component, Input, Output, EventEmitter, NgZone, forwardRef, AfterViewInit,
    OnDestroy, Directive, ElementRef, Host
} from '@angular/core';
```

Definition in the component constructor

```javascript
constructor(private el: ElementRef, private zone: NgZone) {
```

Use of this.zone.runOutsideAngular\(\(\) =&gt; {

to switch execution zone

```javascript
   /**
     * init slick
     */
    initSlick() {
        const self = this;

        this.zone.runOutsideAngular(() => {
            this.$instance = $(this.el.nativeElement).slick(this.config);
            this.initialized = true;

            this.$instance.on('afterChange', (event, slick, currentSlide) => {
                self.zone.run(() => {
                    self.afterChange.emit({event, slick, currentSlide});
                });
            });

            this.$instance.on('beforeChange', (event, slick, currentSlide, nextSlide) => {
                self.zone.run(() => {
                    self.beforeChange.emit({event, slick, currentSlide, nextSlide});
                });
            });

            this.$instance.on('breakpoint', (event, slick, breakpoint) => {
                self.zone.run(() => {
                    self.breakpoint.emit({event, slick, breakpoint});
                });
            });

            this.$instance.on('destroy', (event, slick) => {
                self.zone.run(() => {
                    self.destroy.emit({event, slick});
                });
            });
        });
    }
```

### Add even, odd and last class to ngFor

```text
div(
    *ngFor="let item of item; let last = last; let odd = odd; let even = even; let index = index;",
    [ngClass]="{'odd': odd,'even': even,'last': last}", 
    class="item item-{{ index }}")
```

will result in

```markup
<div class="item odd item-1">
First item
</div>
<div class="item even item-2">
Second item
</div>
<div class="item odd last item-2">
Third item
</div>
```

### Dynamic templates

In angular 2 your can use dynamic templates called by name Primeng library make heavy use of it, you can see as an illustration [templates definitions here](https://github.com/primefaces/primeng/blob/master/src/app/components/common/shared.ts)

### Injection parent component in child component

Example and explanations in the [slick-carousel integration](https://hackernoon.com/wrap-any-jquery-plugin-with-angular-2-component-case-study-8b00eacec998) tutorial

* **@ContentChildren\(\)** allow  to have a reference to a child component in the parent component 
* **@Host\(\)** allow  to have a reference to a parent component in the child component 

```typescript
@Directive({
  selector: '[slick-carousel-item]',
})
export class SlickCarouselItem {
  constructor(private el: ElementRef, @Host() private carousel: SlickCarouselComponent) {
  }
  ngAfterViewInit() {
    this.carousel.addSlide(this);
  }
  ngOnDestroy() {
    this.carousel.removeSlide(this);
  }
}
```

### Http interceptor

Http interceptor intercept http requests for example to add a token to all API request.

Define interceptor service in the app.module.ts

Example of interceptor file

### Execute a function with a delay in an angular component

### Use environment variable in your component or service

[https://medium.com/beautiful-angular/angular-2-and-environment-variables-59c57ba643be](https://medium.com/beautiful-angular/angular-2-and-environment-variables-59c57ba643be)

### Async handling automation and Progressive Web app

[https://medium.com/@cyrilletuzi/angular-async-pipe-everywhere-with-ngx-pwa-offline-d8de68845c81](https://medium.com/@cyrilletuzi/angular-async-pipe-everywhere-with-ngx-pwa-offline-d8de68845c81)

### Sharing data / method between component

[https://angularfirebase.com/lessons/sharing-data-between-angular-components-four-methods/](https://angularfirebase.com/lessons/sharing-data-between-angular-components-four-methods/)

### Setup of universal server side rendering \(updated\)

[https://angularfirebase.com/lessons/server-side-rendering-firebase-angular-universal/](https://angularfirebase.com/lessons/server-side-rendering-firebase-angular-universal/)\`

### Angular Forms : setValue vs patchValue 

[https://ultimatecourses.com/blog/angular-2-form-controls-patch-value-set-value](https://ultimatecourses.com/blog/angular-2-form-controls-patch-value-set-value)

### Return a mock if server is off 



```text
getTasks(): Observable<Tasks[]> {
    return this.httpClient
      .get<Tasks[]>(URL.forTasks())
      .pipe(catchError(() => of(TASKS_MOCK)));
  }
```

### Multiple service calls

{% embed url="https://coryrylan.com/blog/angular-multiple-http-requests-with-rxjs" %}

### Router lazy load nested path 

{% embed url="https://medium.com/ngconf/how-to-nest-lazy-loaded-modules-2d73a7881be" %}




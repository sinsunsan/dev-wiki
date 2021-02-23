# Build a library module

### Type of library 

Angular libraries can come in different shapes and for different purposes!

* **utils** — a collection of various utilities, usually in form of stateless services
* **component library** — a collection of reusable simple \(dumb\) components with only plain API facilitated using mostly `@Input` and `@Output` decorators
* **drop in component** — a more complex component with its own state handling / data fetching which can still communicate with the parent application using `@Input` and `@Output` \(eg pass in configuration or let the parent know about the outcome of some operation…\)
* **sub-application** — the most complex library which could also run as a stand alone application if the need be. Such a library can come with multiple modules with their own routes, components and services…  List taken from this [article](https://medium.com/@tomastrajan/why-and-how-to-lazy-load-angular-libraries-a3bf1489fe24)

### Global explanation of how to set up a lib for Angular 

{% embed url="https://angular.io/guide/creating-libraries" caption="Official guide page" %}

{% embed url="https://medium.com/@tomsu/how-to-build-a-library-for-angular-apps-4f9b38b0ed11" %}

{% embed url="https://www.youtube.com/watch?v=lvjt9rBHWjo" %}

{% embed url="https://www.youtube.com/watch?v=l3wjN4datGs" %}

{% embed url="https://medium.com/better-programming/angular-7-series-part-2-create-custom-library-8d7a0494b2cc" caption="check list of steps to create a lib" %}

### 

### Theming 

{% embed url="https://medium.com/@tarangkhandelwal/theming-angular-app-its-libraries-8f9e46168751" %}

{% embed url="https://github.com/angular/components/tree/master/src/material" caption="Angular Material inspirations " %}

{% embed url="https://www.freecodecamp.org/news/how-to-create-themes-for-your-angular-7-apps-using-css-variables-69251690e9c5/" %}

{% embed url="https://www.freecodecamp.org/news/everything-you-need-to-know-about-css-variables-c74d922ea855/" %}

{% embed url="https://medium.com/angular-in-depth/the-ultimate-guide-to-set-up-your-angular-library-project-399d95b63500" %}

### 

### Make library configurable  

For short we need to use an injection token and a provider in the  module definition of the lib and use forRoot in the consuming app.

{% embed url="https://www.usefuldev.com/post/Angular:%20Creating%20configurable%20libraries%20with%20angular%20cli" %}

###  

### Module resolution and library 

* How the modules of dist/library are available for all app without being a node module 

Thanks to path additions of tsconfig.json added at the time of doing **`ng generate library my-lib`**

[https://www.typescriptlang.org/docs/handbook/module-resolution.html\#base-url](https://www.typescriptlang.org/docs/handbook/module-resolution.html#base-url)

### 

### Get the assets of the library in dist folder 

This issue is not more valid from angular 9

{% embed url="https://github.com/linnenschmidt/build-ng-packagr\#how-to-use-it" %}

{% embed url="https://blog.clairvoyantsoft.com/assets-support-for-angular-7-library-b3ceb0c7484b" %}

{% embed url="https://www.digitalocean.com/community/tutorials/angular-custom-svg-icons-angular-material" %}

### 

### Publish the npm package 

* Use an open source free private npm package

{% embed url="https://github.com/verdaccio/verdaccio" caption="Open source private npm proxy" %}

* Or use `npm pack` in dist/my-lib folder and npm install from this npm pack [https://docs.npmjs.com/cli-commands/pack.html](https://docs.npmjs.com/cli-commands/pack.html)

{% page-ref page="../npm/" %}

### Workspace \(Angular CLI or NX\) + Lazy loading and routing

{% embed url="https://github.com/angularlicious/lazy-load-library-micro-app" %}

{% embed url="https://medium.com/@angularlicious/lazy-load-angular-library-micro-applications-648c947821c3" %}

{% embed url="https://nx.dev/angular" %}

{% embed url="https://medium.com/@tomastrajan/why-and-how-to-lazy-load-angular-libraries-a3bf1489fe24" %}




---
layout: post
title: Practical guide to use angular 2 universal starter
published: true
---

# 2017-02-23-how-to-use-the-angular-universal-starter

## This tutorial is quick old and no relevant any more

You can find updated information in the angular university article about [angular universal](https://blog.angular-university.io/angular-universal/)

### Outdated article

Angular Universal allow to do server side rendering of the angular code. Waiting front end code generate the page.

It allow that even if a user act on the page \(click on items, change page...\), the changes occurring in the server rendered side are replayed in the client rendered page.

So the end user will not see anything except it will be faster, Whereas google will see all the pages as though it were a normal user.

Look at this article to [have a more global view on angular universal](http://dev.sebastienlucas.com/universal-angular/).

### Look at other starter of examples

I've stumbed upon other starter that we find in the universal angular repository itself. They seem much simpleer that universal starter so per aps it is a good idea to test them

* [Hello World starter](https://github.com/angular/universal/tree/master/examples/hello-world)
* [Other examples](https://github.com/angular/universal/tree/master/examples)

## Clone the angular universal starter

* Universal angular starter  

  [https://github.com/angular/universal-starter](https://github.com/angular/universal-starter)

## What file do what?

Here is the schema that I borrow from this [good article](https://medium.com/google-developer-experts/angular-universal-for-the-rest-of-us-922ca8bac84) by Wassim Chegham on Medium, that explain the role of each file.

![Files structure explained](https://github.com/sinsunsan/dev-wiki/tree/e91a89337cb472fad5198a7110a0eaa8d63d66f5/images/universal-files.png)

## Some vocabulary to start

For convenience let's use the following acronyms.

* **SSR** : Server side rendering
* **CSR** : Client side rendering

## Explanation of the role of each file in angular starter

### Files in the src folder

[src folder code on github](https://github.com/angular/universal-starter/tree/master/src)

In this folder are the files to be reused in your application.

### Files to handle SSR \(Server Side Rendering\)

* **node.module.ts** : The equivalent of browser.module \(@ngmodule definition but for SSR\)
* **server.routes.ts** : The definition of the route server side. Only those routes will be rendered by the back.

```javascript
/**
 * Server-side routes. Only the listed routes support html5pushstate.
 * Has to match client side routes.
 *
 * Index (/) route does not have to be listed here.
 **/
export const routes: string[] = [
  'app/fr',
  'app/fr/home'
  // list  more routes you want to be prerendered
];
```

* **server.aot.ts** : AOT version
* **server.ts** : This file is the settings of the express server that render the page.

On thing that can be customised here is the directory of static assets

Here we set images and css folder to be accessible from [http://localhost:3000/images](http://localhost:3000/images) and [http://localhost:3000/css](http://localhost:3000/css)

```javascript
app.use(
  '/images',
  cacheControl,
  express.static(path.join(__dirname, '..', '..', '..', 'images'), {
    maxAge: 30
  })
);
app.use(
  '/css',
  cacheControl,
  express.static(path.join(__dirname, '..', '..', '..', '..', 'build', 'css'), {
    maxAge: 30
  })
);
```

As we have installed angular starter as a sub-directory in our project, we need to go back with the handy **path.join** syntax.

.. Mean go back one folder

### Files to handle CSR \(Client Side Rendering\)

_To be configured or customized_

* **browser.module.ts** Main angular @ngmodule for client side will replace your current MainModule or rootModule.

_To keep as if of minimally customized_

* **\_\_workaround.browser.ts** : Patch of angular core \(useful till angular v4\) for CSR \(Client Side Rendering\) called by client.ts
* **client.aot.ts** : bootstrap file version for AOT \(Ahead of Time compilation\)
* **client.ts** : bootstrap file for non AOT settings.

The main features of bootstrap files is the replace the the standard bootstraper With a specific one. So this 3 lines are important :

```javascript
import { platformUniversalDynamic } from 'angular2-universal/browser';

// ...  More code

export const platformRef = platformUniversalDynamic();

platformRef.bootstrapModule(MainModule);

// ...  More code
```

* **\_\_workaround.node.ts** : Patch of angular core \(useful till angular v4\) for SSR \(Server Side Rendering\)

In this file is an example of a definition of a main @ngmodule that you should use or replicate if you want to be universal angular compatible.

### Files used by both

* **index.html**

The [index.html](https://github.com/angular/universal-starter/blob/master/src/index.html) is pretty standard and you can use yours but mind the line at the end. That insert the bundled file that is compiled by webpack. You should do the same

* **typings.d.ts** An ambient type definition file that add typings to the variable used in this library. [Look at the code](https://github.com/angular/universal-starter/blob/master/src/typings.d.ts) to learn more about how to define types this way.
* **angular2-meta.ts** [File code](https://github.com/angular/universal-starter/blob/master/src/angular2-meta.ts). Related to the way meta tags \(the tags at the top of HEAD section of the html documented is handled\)

### Files in the src/app folder

[scr/+app folder on github](https://github.com/angular/universal-starter/tree/master/src/%2Bapp)

The files and sub-directories in this folder represent an example app with different cases you may encounter \(lazy loading, loading data from an api..\)

This is just an example app and you probably won't need it.

An exception could be a cache service

In [universal-starter/src/+app/shared/](https://github.com/angular/universal-starter/tree/master/src/%2Bapp/shared)

You may reuse some file to make the optional but recommended cache system functional in your app too.

### package.json of the universal starter

Specific parts to be added for universal rendering

```javascript
{

// Equivalent o platform browser but for the server
"@angular/platform-server": "~2.1.2",

// Deal with initialization
"@angularclass/bootloader": "~1.0.1",
"@angularclass/idle-preload": "~1.0.4",

// Rendering engine for express that know angular 2
"angular2-express-engine": "~2.1.0-rc.1",
"angular2-platform-node": "~2.1.0-rc.1",

// main library for angular 2 universal
"angular2-universal": "~2.1.0-rc.1",

// Some polyfill for the angular or node part
"angular2-universal-polyfills": "~2.1.0-rc.1"
}
```

### Webpack configuration

* **webpack.config.ts**: The webpack config for development

[https://github.com/angular/universal-starter/blob/master/webpack.config.ts](https://github.com/angular/universal-starter/blob/master/webpack.config.ts)

_Common configuration for client and server_

* commonConfig

```javascript
export var clientConfig = {
  target: 'web',
  // We can change the entry point.
  //It is the file that is first read by webpack
  // following all its imports.
  entry: './src/client',
  // We can change the output path
  output: {
    path: root('dist/client')
  },
  node: {
    global: true,
    crypto: 'empty',
    __dirname: true,
    __filename: true,
    process: true,
    Buffer: false
  }
};
```

* commonPlugins

_Specific server configuration_

* serverConfig
* serverPlugins

_Specific client configuration_

* clientConfig
* clientPlugins
* **webpack.prod.config.ts**: The webpack config for prod

[https://github.com/angular/universal-starter/blob/master/webpack.prod.config.ts](https://github.com/angular/universal-starter/blob/master/webpack.prod.config.ts)

### Angular universal debugging

* How to know you have a problem ?

This error message should show "Error in SSR, serving for direct CSR" It means that the backend is just serving index.html and not being able to do any server side prerendering because of a problem.

* **Error: This method is not implemented in Parse5DomAdapter: getCookie**

This error seem to be caused by http service. Angular universal is overriding http service, and depending of the position of the declaration of angular universal module in the @ngmodule it can be not the last version.

So look at the error stack, if you find something that is related to http call, try to comment the module, that do that first to check.

At least it is what is explained in this [issue](https://github.com/angular/universal/issues/536#issuecomment-247762794)

[Why http module is being overridden in universal module by MarkPieszak](https://github.com/angular/universal/issues/536#issuecomment-268810295)

> Well it depends on which Modules you're using, usually it can be first, but depending on if other Modules are overriding Http as well, sometimes you need to re-position it. I can't remember why Material is using Http, but in Universal we override it because we need to keep track of all requests, so we can determine when the App is stable, to then serialize it.

* **ReferenceError: document is not defined**

You probably have imported **UniversalModule** several times in your code.

* **Only "Error in SSR, serving for direct CSR" with no more detail**

Go to your browser load the page, I should see an error in the console. I assume that it is the same error that occured in the backend.

### isBrowser or isNode

This two utility functions allow each part to know if they are browser side or server side.

```javascript
import { isBrowser, isNode } from 'angular2-universal';

export class myComponent {

  if (isBrowser()) {
    // Only client side stuff
    // document.
    // window.
  } else {
    // simpler display but no error
  }
}
```

### Package json scripts and explanation

```javascript
"scripts": {
    "watch": "webpack --watch",
    "watch:dev": "npm run server & npm run watch",
    "clean:dist": "rimraf dist",
    // clean ngc files (aoc compilation)
    "clean:ngc": "rimraf **/*.ngfactory.ts **/*.css.shim.ts",
    "prebuild": "npm run clean:dist",
    // for normal build (not prod) we do  not use --config webpack.config.ts
    // as webpack.config.ts is the default name webpack will search for
    "build": "webpack  --progress",
    "build:prod:ngc": "npm run clean:ngc && npm run ngc && npm run clean:dist && npm run build:prod",
    "build:prod:ngc:json": "npm run clean:ngc && npm run ngc && npm run clean:dist && npm run build:prod:json",
    "build:prod": "webpack --config webpack.prod.config.ts",
    "build:prod:json": "webpack --config webpack.prod.config.ts --json | webpack-bundle-size-analyzer",
    "ngc": "ngc -p tsconfig.aot.json",
    "prestart": "npm run build",
    // run the express server (by default on port 3000) using
    // web pack bundled dist/server/index.js file
    "server": "nodemon dist/server/index.js",
    // Run the server in a way that it is inspectable (with breakpoint in chrome)
    "debug:server": "node --inspect --debug-brk dist/server/index.js",
    "start": "npm run server",
    "debug:start": "npm run build && npm run debug:server",
    "predebug": "npm run build",
    "debug:build": "node-nightly --inspect --debug-brk node_modules/webpack/bin/webpack.js",
    "debug:build:prod": "node-nightly --inspect --debug-brk node_modules/webpack/bin/webpack.js  --config webpack.prod.config.ts",
    "debug": "node --debug-brk dist/server/index.js"
  },
```


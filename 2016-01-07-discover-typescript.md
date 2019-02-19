---
layout: post
title: Typescript / The future of javascript now!
published: true
---

Typescript is a subset of javascript. That mean that all javascript ES5, 6 ... is valid typescript, but typescript add many useful features. The more important is the hard typings but not only.

Like ES6 and all new javascript brand, it need to be compiled to current javascript so that actual browsers can interpret it.

### Resources

* Type script official documentation
[https://www.typescriptlang.org/](https://www.typescriptlang.org/)

* An open source book on typescript
[https://basarat.gitbooks.io/typescript](https://basarat.gitbooks.io/typescript)

###  Questions about d.ts file

* **what is a d.ts files** :   
A d.ts file is a definition file created to make available typings for libraries that do not use typescript.

* **how typescript know where the types definition the d.ts file is ?**    
Types definitions are informed in the package.json of the library.
In our sweetalert2 example
`"types": "sweetalert2.d.ts",` the following key is enough to tell typescript that the type definition file is at the root of the library in a file named **sweetalert2.d.ts**.

### Example of a d.ts file

[https://github.com/limonte/sweetalert2/blob/master/sweetalert2.d.ts](https://github.com/limonte/sweetalert2/blob/master/sweetalert2.d.ts)

Definition of the main function of sweealert 2 ( a library to display nice alert confirm modal

```js
function swal(title: string, message?: string, type?: SweetAlertType): Promise<any>;
```

The function parameters are defined only. Not the content of the function as it is not the purpose of the typescript definition file (d.ts). This file purpose is to add the information about the types used and expected in the js files of existing libraries not written directly in typescript.

Let's start to identify the syntax of function parameters :

* **title** is the first argument and should be a string
* **message** is the second argument and should be a string, it is an optional parameter it don't produce an error if not provided.
* **type** is optional and is not using a standard type but a custom type SweetAlertType that is defined elsewhere
* **`: Promise<any>`** refer to what the function should return. It should return a Promise with a collection / array of element of any types

Then we follow with the definition of an interface. Interface is the definition of an empty object that serve as a model to constrain object with real data in it. It serve as a guide for developer that in the code use an implementation of this same object. It serve to define what we called custom types, types are not the standard string, boolean....


```js
 export interface SweetAlertOptions {
        /**
         * The title of the modal, as HTML.
         * It can either be added to the object under the key "title" or passed as the first parameter of the function.
         * Default: null
         */
        title?: string;

        /**
         * The title of the modal, as text. Useful to avoid HTML injection.
         * Default: null
         */
        titleText?: string;

        // More fields definition
   }
```

 An other syntax is alternative types
 ` width?: number|string;`  
 Here we allow either number either string for the optional property 'width' of the SweetAlertOptions object.


 We identify also this syntax
`preConfirm?: (inputValue: any) => Promise<any>;`
it defined a function with the new ES6 syntax called fat arrow syntax =>
So this function assigned to optional `preconfirm` property need an argument `inputValue` of any type
that return a promise with a collection of element of any type.

All this types declaration is wrapped in a
`declare module "sweetalert2" {`  
that allow to map the declaration with module name `sweetalert2`that is defined in the main sweetalert2 js file

### Contribute to create d.ts files

* The following in depth tutorial explain how to create a definition files for an existing library. Seems boring? Could be a great way to explore libraries and read their code and learn from them [http://blog.wolksoftware.com/contributing-to-definitelytyped](http://blog.wolksoftware.com/contributing-to-definitelytyped)
* The main libraries types is stored in the huge [Definetly typed](https://github.com/DefinitelyTyped/DefinitelyTyped) repository. 
* It is possible to import only a single library types from this same repo with for example `npm install @types/lodash` for lodash only

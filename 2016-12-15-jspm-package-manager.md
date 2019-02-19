---
published: true
layout: post
title: JSPM A good alternative to web pack
---

# 2016-12-15-JSPM-package-manager

Jspm is an alternative to using webpack. It's philosophy is quite different and intersting. Here is what you need to know about it.

## JSPM online

The main site [http://jspm.io/](http://jspm.io/)

The [documentation of jspm on github](https://github.com/jspm/jspm-cli/tree/master/docs)

## In short

* JSPM use existing Package managers : NPM & Github
* JSPM manage the config.js file to be used by system.js
* JPSM store it's information is 2 places: the **package.json** and the **config.js** file The first one is used by NPM and allow to reproduce the exact JSPM installation The second is used by system.js and allow to the JS module loader to do the mapping between named `import import * from { @angular }` and the exact location of the file in the `jspm_packages`

## How JSPM deal with version

jspm install installs the latest versions of packages listed in the package.json respecting semver ranges defined in it.

Once installed, exact versions numbers\(not ranges\) are stored in jspm's config.js. The subsequent jspm installs will install concrete versions stored in the config.js

## version required by the app & versions required by the libs

JSPM install version required by the libraries also so it can store and import different versions

Let's inspect the rxjs packages isntalled

```text
jspm inspect npm:rxjs

Installed versions of npm:rxjs

       rxjs 5.0.1 (^5.0.1)

       npm:@angular/core@2.3.1
         rxjs 5.0.0-rc.4 (5.0.0-rc.4)

       npm:@angular/http@2.3.1
         rxjs 5.0.0-rc.4 (5.0.0-rc.4)

       npm:@angular/router@3.3.1
         rxjs 5.0.0-rc.4 (5.0.0-rc.4)

       npm:angularfire2@2.0.0-beta.6-preview
         rxjs 5.0.0-beta.12 (5.0.0-beta.12)
```

### Download packages

`jspm update` Update libraries to their latest version in the range defined in the package.json `jspm inspect` List all exact version install by jspm `jspm install` Reinstall all libraries following package.js stored jspm formula


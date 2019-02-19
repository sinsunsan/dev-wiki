---
layout: post
title: Angular source code
published: true
---

# 2017-08-12-angular-source-code

[Angular Tutorials](http://dev.sebastienlucas.com/recommanded-tutorial-for-angular2/) are good to learn about angular. But sometimes reading the source code is more insightful. We do not have the ambition to decipher all angular but just to point some useful places of the code, where it is better to look directly at the code.

## Components of angular

### The router

* [The router code](https://github.com/angular/angular/blob/master/packages/router/src/router.ts#L44)
* [Navigation extras documentation](https://angular.io/api/router/NavigationExtras#fragment) are options of the router

for example

```javascript
// from /results?page=1 to /view?page=1&page=2
this.router.navigate(['/view'], { queryParams: { page: 2 },  queryParamsHandling: "merge" });
```

* [The router\_link directive](https://github.com/angular/angular/blob/4.3.4/packages/router/src/directives/router_link.ts#L18-L155) It is useful to create a href link  in a dynamic way, If you use a simple href, it is note known by angular and will reload all the angular bootstrap...


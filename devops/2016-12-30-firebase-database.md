---
published: true
title: How to use Firebase in a node / angular app
---

# Firebase database

Firebase is service developed by Google and integrated in google cloud, that allow to have JSON data store type database online.

## What is firebase database

* a service bought by Google in 2014 then integrated in Google ecosystem

  and specifically google storage

  Firebase is available here : [firebase.google.com](https://firebase.google.com)

* a realtime database &gt; the changes will be pushed to all the clients
* a simple JSON Tree structure /projects/344 will store a JSON representing this specific project

## Tools for firebase

* A desktop software to manage your firebase database in a more powerful way than online console [https://firebaseadmin.com](https://firebaseadmin.com)

![Firebase admin desktop app](https://github.com/sinsunsan/dev-wiki/tree/e91a89337cb472fad5198a7110a0eaa8d63d66f5/%7B%7Bsite.baseurl%7D%7D/images/firebase-admin.png)

A full list of utiliies for firebase is available here [https://github.com/afonsopacifer/awesome-firebase](https://github.com/afonsopacifer/awesome-firebase)

### Limitations

* Firebase have a limited query api

This [post](http://stackoverflow.com/questions/26700924/query-based-on-multiple-where-clauses-in-firebase%20) describe the current limitations, impossible to filter by multiple clause. And 3 workaround, filter on the front, compound keys or index.

Other are working on a library to be able to do [where](https://github.com/davideast/Querybase) style query

## How to set it up in the backend with node.js

* you need to add the SDK

  [https://firebase.google.com/docs/admin/setup](https://firebase.google.com/docs/admin/setup)

* Look at the [quick start example app](https://github.com/firebase/quickstart-nodejs)

## how to set it up in the front end with angular 2

* Use Angular fire2


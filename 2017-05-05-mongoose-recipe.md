---
layout: post
title: Mongoose recipe
published: true
---

# 2017-05-05-mongoose-recipe

Mongoose is a nice ORM on top of mongo. I've used it in all the node.js backend I've worked on. Unfortunately its documentation is not its better aspect and lack of examples. Hopefully these recipes could help you achieve what you want

## Field definition

## Property of fields

* **type**: type of data
  * Date
  * Boolean
  * String
  * Number
  * ObjectId: Reference to another Object need to have a ref property mentioning the name of the collection of the ref object
* **ref**: reference to an object to another collection `type: 'ObjectIf', ref: 'users'`
* **default**: Value to set if non is set, defaulting to false
* **unique**: true \| false / Defaulting to false Useful for email or id that need to be unique in the whole collection

### Date field in ISO date or time stamp

To choose timestamp format just set field type as Number.

Defaulting with Date.now note that though the javascript Date.now\(\) is a function we dropped the \(\) for mongoose field definition

```javascript
// ISO Date format
posted: { type: Date, default: Date.now },
// Timestamp Date format
postedTimestamp: { type: Number,default: Date.now },
```


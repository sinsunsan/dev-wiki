---
published: true
title: Node.js libraries  and  modules you should use
---

# Best libraries for node.js

Here is a growing selection of the most useful libraries for node.

## Node JS Core modules

* **PATH** Allow to work on path and urls. Split a path, take the file name... [https://nodejs.org/api/path.html](https://nodejs.org/api/path.html)
* **FS** : Allow to work on file to save file on disk... [https://nodejs.org/api/fs.html](https://nodejs.org/api/fs.html)

## Libraries for Node.js

### Express

* **CORS** : Middleware to help make a CORS settings! [https://github.com/expressjs/cors](https://github.com/expressjs/cors)
* **Morgan** : Http request logging Middleware Similar to the apache log, log the request that express made with the level of information you wish [https://github.com/expressjs/morgan](https://github.com/expressjs/morgan)

### Logging

* **Winston**    

  Log action to a file or database, or online service

  [https://github.com/winstonjs/winston](https://github.com/winstonjs/winston)

### Utilities

* **Lodash** : the utility library for javascript    

  [https://lodash.com](https://lodash.com)

### Http

* **Request && Request promise**    

  Popular library to do http requests in an easy and powerful way.

  can pipe the result to other requests or to a file stream...

[https://github.com/request/request](https://github.com/request/request)

It's port with promise powered by blue bird [https://github.com/request/request-promise](https://github.com/request/request-promise)

### Async & Promises

* **Async** : Aynschronous call \(a sort of lodash for asynchronous operation\) [http://caolan.github.io/async/docs.html\#](http://caolan.github.io/async/docs.html#)
* **Blue bird** : Blue bird is the more popular promise library for node.js Though promise are in the core node.js language there are [multiple arguments](http://stackoverflow.com/questions/34960886/are-there-still-reasons-to-use-promise-libraries-like-q-or-bluebird-now-that-we) to keep using a library like blue bird.

[http://bluebirdjs.com/](http://bluebirdjs.com/)

### Caching

* **Node Cache manager** This library seems to be the more complete. The advantage of this caching library is that it decoupled caching storage from caching configuration so it is possible to cache in redis, memory, file system.... [https://github.com/BryanDonovan/node-cache-manager](https://github.com/BryanDonovan/node-cache-manager)
* **Memory cache \(also node-cache in github\)** This library seems to be the more popular thanks to its simplicity Example implementation in that [tuto](https://goenning.net/2016/02/10/simple-server-side-cache-for-expressjs) [https://github.com/ptarjan/node-cache](https://github.com/ptarjan/node-cache)
* **Express Redis cache** Example implementation in that [tuto](https://goenning.net/2016/02/10/simple-server-side-cache-for-expressjs) [https://github.com/rv-kip/express-redis-cache](https://github.com/rv-kip/express-redis-cache)
* **Node Caching** [https://github.com/mape/node-caching](https://github.com/mape/node-caching)
* **Node cache** [https://github.com/mpneuried/nodecache](https://github.com/mpneuried/nodecache)

### Uploading

* **Multer** Node.js middleware for handling `multipart/form-data`. &gt; handle image upload more easily. Multer is based on busboy.

[https://github.com/expressjs/multer](https://github.com/expressjs/multer)

* **busboy** File multi part upload parser

[https://github.com/mscdex/busboy](https://github.com/mscdex/busboy)

* **gridfs-stream** Mongodb file streamer to save with gridFS

[https://github.com/aheckmann/gridfs-stream](https://github.com/aheckmann/gridfs-stream)

* **node-formidable** Parser for form and upload    

  [https://github.com/felixge/node-formidable](https://github.com/felixge/node-formidable)

### Image manipulation

* **Jimp** : Image processing in javascript without any external dependencies [https://github.com/oliver-moran/jimp](https://github.com/oliver-moran/jimp)
* **Graphic magic** : Image resizing...

[http://aheckmann.github.io/gm/](http://aheckmann.github.io/gm/)

### Export, parser

* **XLS Parser**  XlS Parser

[https://github.com/mgcrea/node-xlsx](https://github.com/mgcrea/node-xlsx)

* **Node excel Export** : Export to excel [https://github.com/functionscope/Node-Excel-Export](https://github.com/functionscope/Node-Excel-Export)
* **node Excel Export** : Lees popular but the config seems more complete... and the doc is better

[https://github.com/andreyan-andreev/node-excel-export](https://github.com/andreyan-andreev/node-excel-export)

* **json2xls** Transform a json to a xls with no settings at all \(using "excel-export": "~0.3.11" in the background\) [https://github.com/rikkertkoppes/json2xls/commits/master](https://github.com/rikkertkoppes/json2xls)
* **js-xls** a js framework to parse xls, and more generally spreadsheet formats... [https://github.com/SheetJS/js-xlsx](https://github.com/SheetJS/js-xlsx)

### Error handling

* **pretty-error** Display errors && error stack in a more elegant way     

  [https://github.com/AriaMinaei/pretty-error](https://github.com/AriaMinaei/pretty-error)

### Templates

* **consolidate** Consolidate template engines...to have a  single API for all !

[https://github.com/tj/consolidate.js/](https://github.com/tj/consolidate.js/)

### Mongoose plugins

* **mongoose simple random** add findOneRandom && findRandom to get random document

  [https://github.com/larryprice/mongoose-simple-random](https://github.com/larryprice/mongoose-simple-random)

* **mongoose-autopopulate**
* **mongoose-deep-populate**


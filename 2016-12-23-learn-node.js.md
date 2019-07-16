---
published: true
title: Tutorials to learn node.js
---

# Learn node.js

Node.js is quite straightforward and easy to learn once we have understood the basics. Though it is a huge ecosystem and there is a lot to learn to master it. The good thing is that it is in javascript. And the more you learn javascript for the backend, the more you master it in the front.

The module system for example has played an important role in the ES6 modules adoption. Indeed modules \(require in node.js\) are so convenient and natural to split the code in different files.

## Modules

* **OS module** : operation system related function

[https://nodejs.org/api/os.html\#os\_os\_tmpdir](https://nodejs.org/api/os.html#os_os_tmpdir)

## Express

## Http call

* Using Request library     [https://blog.risingstack.com/node-hero-node-js-request-module-tutorial](https://blog.risingstack.com/node-hero-node-js-request-module-tutorial/)

## Async, Promises

* Async programming [https://blog.risingstack.com/node-hero-async-programming-in-node-js/](https://blog.risingstack.com/node-hero-async-programming-in-node-js/)
* How to use promises instead of callback and even transform core modules in promise style [https://strongloop.com/strongblog/promises-in-node-js-an-alternative-to-callbacks/](https://strongloop.com/strongblog/promises-in-node-js-an-alternative-to-callbacks/)
* Chaining promises [https://html5hive.org/how-to-chain-javascript-promises/](https://html5hive.org/how-to-chain-javascript-promises/)

[http://stackoverflow.com/questions/28250680/how-do-i-access-previous-promise-results-in-a-then-chain](http://stackoverflow.com/questions/28250680/how-do-i-access-previous-promise-results-in-a-then-chain)

* Using ES6 promises implementation of a library \(blue bird, q....\)

[http://stackoverflow.com/questions/34960886/are-there-still-reasons-to-use-promise-libraries-like-q-or-bluebird-now-that-we](http://stackoverflow.com/questions/34960886/are-there-still-reasons-to-use-promise-libraries-like-q-or-bluebird-now-that-we)

## Error Handling

[https://www.joyent.com/node-js/production/design/errors](https://www.joyent.com/node-js/production/design/errors)

## Performance

* How to get node backend faster [https://engineering.gosquared.com/making-dashboard-faster](https://engineering.gosquared.com/making-dashboard-faster)
* Simple server side cache for express js \(using memory-cache\) [https://goenning.net/2016/02/10/simple-server-side-cache-for-expressjs/](https://goenning.net/2016/02/10/simple-server-side-cache-for-expressjs/)

## Debug

The node debugger that use chrome debugger is available in latest version of node using the --inspect flag

```text
$ node --inspect index.js
Debugger listening on port 9229.
Warning: This is an experimental feature and could change at any time.
To start debugging, open the following URL in Chrome:
    chrome-devtools://devtools/remote/serve_file/@60cd6e859b9f557d2312f5bf532f6aec5f284980/inspector.html?experiments=true&v8only=true&ws=localhost:9229/b4f005c7-caad-4e7c-b554-5746da12b549
Server listening on 3000
Debugger attached.
```

## test

* Simple test with mocha and chai tutorial      

  [https://semaphoreci.com/community/tutorials/getting-started-with-node-js-and-mocha](https://semaphoreci.com/community/tutorials/getting-started-with-node-js-and-mocha)

## Inspire from existing library

You will probably use many open source library in your project. Why not opening a dedicated tab or window in your text editor to browse the code. It could be very instructive to how to organize code in node.js.

### Stream

Read and write files with fs

```javascript
var src = fs.createReadStream(req.files.path);
var target_path = '.tmp/' + req.file.originalname + '.xls';
var dest = fs.createWriteStream(target_path);
```


Mocha is a feature-rich JavaScript test framework running on Node.js and in the browser.

Lots of documentation is available on https://mochajs.org/ but here are a couple of notes that can be useful

# npm

* `"test": "mocha --watch" `
  * will launch mocha which is globally installed and log for scripts in the test folder "./test/*.js"
  
* `"test": "mocha --recursive "./spec/*.js"`
  * custom folder to look into can be configured

* `"test:utils": "mocha --config utils/__tests__/.mocharc.js"`
  * --config can precise the location of the config file .mocharc.js
  
*`"test:dev": "mocha  -r mocha.env.js --watch "`
  * `-r` can include a module; useful for exemple to set the environment: 
  e.g `process.env.NODE_ENV = 'development'`
 

# config file .mocharc.js

e.g
```
(module.exports = {
    diff: true,
    extension: ['js'],
    package: './package.json',
    reporter: 'spec',
    slow: 75,
    timeout: 2000,
    ui: 'bdd',
    'recursive':['./utils/**/*.spec.js'],
    'watch-files': ['./utils/**/*.js', '**/*.spec.js'],
    'watch-ignore': ['lib/vendor']
})
```

more details and ideas for configuration on https://mochajs.org/#command-line-usage





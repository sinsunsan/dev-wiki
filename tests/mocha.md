# Mocha

Mocha is a feature-rich JavaScript test framework running on Node.js and in the browser.

Lots of documentation is available on [https://mochajs.org/](https://mochajs.org/) but here are a couple of notes that can be useful

## NPM

* `"test": "mocha --watch"`
  * will launch mocha which is globally installed and log for scripts in the test folder "./test/\*.js"
* `"test": "mocha --recursive "./spec/*.js"`
  * custom folder to look into can be configured
* `"test:utils": "mocha --config utils/__tests__/.mocharc.js"`
  * --config can precise the location of the config file .mocharc.js

\*`"test:dev": "mocha -r mocha.env.js --watch "`

* `-r` can include a module; useful for exemple to set the environment: 

  e.g `process.env.NODE_ENV = 'development'`

## Config file .mocharc.js

e.g

```text
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

more details and ideas for configuration on [https://mochajs.org/\#command-line-usage](https://mochajs.org/#command-line-usage)

## Code coverage

* Install [Istambul](https://istanbul.js.org/) package `npm i nyc --save-dev`
* Edit the package.json to perform the coverage check of the test:

  ```text
  {
  "scripts": {
    "test": "nyc --reporter=text mocha"
  }
  }
  ```


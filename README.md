# api documentation for  [convict (v3.0.0)](https://github.com/mozilla/node-convict)  [![npm package](https://img.shields.io/npm/v/npmdoc-convict.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-convict) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-convict.svg)](https://travis-ci.org/npmdoc/node-npmdoc-convict)
#### Unruly configuration management for Node.js

[![NPM](https://nodei.co/npm/convict.png?downloads=true)](https://www.npmjs.com/package/convict)

[![apidoc](https://npmdoc.github.io/node-npmdoc-convict/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-convict_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-convict/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-convict/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-convict/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Lloyd Hilaiel",
        "email": "lloyd@hilaiel.com",
        "url": "http://lloyd.io"
    },
    "browserify": {
        "transform": [
            "varify"
        ]
    },
    "bugs": {
        "url": "https://github.com/mozilla/node-convict/issues"
    },
    "dependencies": {
        "depd": "1.1.0",
        "json5": "0.5.1",
        "lodash.clonedeep": "4.5.0",
        "minimist": "1.2.0",
        "moment": "2.17.1",
        "validator": "7.0.0",
        "varify": "0.2.0"
    },
    "description": "Unruly configuration management for Node.js",
    "devDependencies": {
        "coveralls": "2.12.0",
        "eslint": "3.17.1",
        "istanbul": "0.4.5",
        "mocha": "3.2.0",
        "mocha-lcov-reporter": "1.3.0",
        "must": "0.13.4",
        "obj_diff": "0.3.0"
    },
    "directories": {},
    "dist": {
        "shasum": "259f30bfb87ee0944860486203519d467b4d51b5",
        "tarball": "https://registry.npmjs.org/convict/-/convict-3.0.0.tgz"
    },
    "engines": {
        "node": ">=4"
    },
    "files": [
        "lib",
        "npm-shrinkwrap.json"
    ],
    "gitHead": "78d9621562c15f6234bf65f5212ed9859176cebe",
    "homepage": "https://github.com/mozilla/node-convict",
    "keywords": [
        "configuration",
        "config",
        "key value store",
        "schema",
        "nested",
        "validation"
    ],
    "license": "Apache-2.0",
    "main": "lib/convict.js",
    "maintainers": [
        {
            "name": "6a68",
            "email": "ohai@6a68.net"
        },
        {
            "name": "fmarier",
            "email": "francois@fmarier.org"
        },
        {
            "name": "lloyd",
            "email": "lloyd@hilaiel.com"
        },
        {
            "name": "ozten",
            "email": "shout@ozten.com"
        },
        {
            "name": "rfkelly",
            "email": "rfkelly@mozilla.com"
        },
        {
            "name": "seanmonstar",
            "email": "sean.monstar@gmail.com"
        },
        {
            "name": "stomlinson",
            "email": "shane@shanetomlinson.com"
        },
        {
            "name": "vladikoff",
            "email": "vlad@vladikoff.com"
        },
        {
            "name": "zaach",
            "email": "zack.carter@gmail.com"
        }
    ],
    "name": "convict",
    "optionalDependencies": {
        "varify": "0.2.0"
    },
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/mozilla/node-convict.git"
    },
    "scripts": {
        "clean": "rm -rf test/coverage",
        "lint": "eslint .",
        "lint:fix": "eslint --fix .",
        "posttest": "npm run lint",
        "posttest:ci": "npm run lint",
        "posttest:coverage": "npm run lint",
        "preversion": "./assert_shrinkwrap_ready",
        "safefreeze": "rm -rf node_modules npm-shrinkwrap.json && npm install --production --registry https://registry.npmjs.org/ && npm dedupe && npm shrinkwrap && npm install && npm test && touch package.json npm-shrinkwrap.json",
        "test": "mocha --check-leaks -R spec",
        "test:ci": "istanbul cover _mocha -- --check-leaks test/*-tests.js && cat test/coverage/lcov.info | coveralls",
        "test:coverage": "istanbul cover _mocha -- --check-leaks test/*-tests.js",
        "version": "./assert_changelog_ready $npm_package_version"
    },
    "version": "3.0.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module convict](#apidoc.module.convict)
1.  [function <span class="apidocSignatureSpan">convict.</span>addFormat (name, validate, coerce)](#apidoc.element.convict.addFormat)
1.  [function <span class="apidocSignatureSpan">convict.</span>addFormats (formats)](#apidoc.element.convict.addFormats)



# <a name="apidoc.module.convict"></a>[module convict](#apidoc.module.convict)

#### <a name="apidoc.element.convict.addFormat"></a>[function <span class="apidocSignatureSpan">convict.</span>addFormat (name, validate, coerce)](#apidoc.element.convict.addFormat)
- description and source-code
```javascript
addFormat = function (name, validate, coerce) {
  if (typeof name === 'object') {
    validate = name.validate;
    coerce = name.coerce;
    name = name.name;
  }
  if (typeof validate !== 'function') {
    throw new Error('Validation function for ' + name + ' must be a function.');
  }
  if (coerce && typeof coerce !== 'function') {
    throw new Error('Coerce function for ' + name + ' must be a function.');
  }
  types[name] = validate;
  if (coerce) converters[name] = coerce;
}
```
- example usage
```shell
...
    }
  },
  default: '3cec609c9bc601c047af917a544645c50caf8cd606806b4e0a23312441014deb'
}
});
'''

Or, you can use 'convict.addFormat()' to register a custom format checking
method that can be reused for many different properties:

'''javascript
convict.addFormat({
name: 'float-percent',
validate: function(val) {
  if (val !== 0 && (!val || val > 1 || val < 0)) {
...
```

#### <a name="apidoc.element.convict.addFormats"></a>[function <span class="apidocSignatureSpan">convict.</span>addFormats (formats)](#apidoc.element.convict.addFormats)
- description and source-code
```javascript
addFormats = function (formats) {
  Object.keys(formats).forEach(function(type) {
    convict.addFormat(type, formats[type].validate, formats[type].coerce);
  });
}
```
- example usage
```shell
...
convict configuration object. The configuration object has an API for getting
and setting values, described below.

### config.addFormat(format)

Adds a new custom format.

### config.addFormats(format1, format2, ...)

Adds new custom formats.

### config.get(name)

Returns the current value of the 'name' property. 'name' can use dot notation to reference nested values. E.g.:
'''javascript
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

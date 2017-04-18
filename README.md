# npmdoc-convict

#### api documentation for  [convict (v3.0.0)](https://github.com/mozilla/node-convict)  [![npm package](https://img.shields.io/npm/v/npmdoc-convict.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-convict) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-convict.svg)](https://travis-ci.org/npmdoc/node-npmdoc-convict)

#### Unruly configuration management for Node.js

[![NPM](https://nodei.co/npm/convict.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/convict)

- [https://npmdoc.github.io/node-npmdoc-convict/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-convict/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-convict/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-convict/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-convict/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-convict/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Lloyd Hilaiel",
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
            "name": "6a68"
        },
        {
            "name": "fmarier"
        },
        {
            "name": "lloyd"
        },
        {
            "name": "ozten"
        },
        {
            "name": "rfkelly"
        },
        {
            "name": "seanmonstar"
        },
        {
            "name": "stomlinson"
        },
        {
            "name": "vladikoff"
        },
        {
            "name": "zaach"
        }
    ],
    "name": "convict",
    "optionalDependencies": {
        "varify": "0.2.0"
    },
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



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

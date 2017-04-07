# api documentation for  [json-mask (v0.3.8)](https://github.com/nemtsov/json-mask#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-json-mask.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-json-mask) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-json-mask.svg)](https://travis-ci.org/npmdoc/node-npmdoc-json-mask)
#### Tiny language and engine for selecting specific parts of a JS object, hiding the rest.

[![NPM](https://nodei.co/npm/json-mask.png?downloads=true)](https://www.npmjs.com/package/json-mask)

[![apidoc](https://npmdoc.github.io/node-npmdoc-json-mask/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-json-mask_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-json-mask/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-json-mask/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-json-mask/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "nemtsov@gmail.com"
    },
    "bugs": {
        "url": "https://github.com/nemtsov/json-mask/issues"
    },
    "dependencies": {},
    "description": "Tiny language and engine for selecting specific parts of a JS object, hiding the rest.",
    "devDependencies": {
        "browserify": "^10.2.6",
        "istanbul": "^0.3.17",
        "mocha": "~1.12.0",
        "standard": "^7.1.0",
        "uglifyjs": "^2.4.10"
    },
    "directories": {},
    "dist": {
        "shasum": "2d66415de14b0e8bc6c1514554a90bfca8356941",
        "tarball": "https://registry.npmjs.org/json-mask/-/json-mask-0.3.8.tgz"
    },
    "gitHead": "cf8457ba617d9ecf749e0a65f38b33f2ce76457a",
    "homepage": "https://github.com/nemtsov/json-mask#readme",
    "keywords": [
        "mask",
        "filter",
        "select",
        "fields",
        "projection",
        "query",
        "json"
    ],
    "license": "MIT",
    "main": "lib/index",
    "maintainers": [
        {
            "name": "nemtsov",
            "email": "nemtsov@gmail.com"
        }
    ],
    "name": "json-mask",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/nemtsov/json-mask.git"
    },
    "scripts": {
        "_build-browser-full": "browserify -s jsonMask -e lib/index.js | sed -e \"s/\\[ *'.*' *\\]/;/\" > build/jsonMask.js",
        "_build-browser-license": "cat build/copyright  | cat - build/jsonMask.js  | tee build/jsonMask.js",
        "_build-browser-min": "cat build/jsonMask.js | uglifyjs --comments > build/jsonMask.min.js",
        "build-browser": "npm run-script _build-browser-full; npm run-script _build-browser-license; npm run-script _build-browser-min",
        "lint": "standard 'lib/**/*.js' 'test/**/*.js'",
        "test": "npm run lint && mocha",
        "test-cov": "istanbul cover _mocha",
        "test-watch": "mocha -w -G -R min"
    },
    "testling": {
        "browsers": [
            "ie/8..latest",
            "firefox/16..latest",
            "firefox/nightly",
            "chrome/22..latest",
            "chrome/canary",
            "opera/12..latest",
            "opera/next",
            "safari/5.1..latest",
            "ipad/6.0..latest",
            "iphone/6.0..latest",
            "android-browser/4.2..latest"
        ],
        "harness": "mocha",
        "files": "test/*.js"
    },
    "version": "0.3.8"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module json-mask](#apidoc.module.json-mask)
1.  [function <span class="apidocSignatureSpan">json-mask.</span>compile (text)](#apidoc.element.json-mask.compile)
1.  [function <span class="apidocSignatureSpan">json-mask.</span>filter (obj, compiledMask)](#apidoc.element.json-mask.filter)
1.  object <span class="apidocSignatureSpan">json-mask.</span>util

#### [module json-mask.util](#apidoc.module.json-mask.util)
1.  [function <span class="apidocSignatureSpan">json-mask.util.</span>has (obj, key)](#apidoc.element.json-mask.util.has)
1.  [function <span class="apidocSignatureSpan">json-mask.util.</span>isArray ()](#apidoc.element.json-mask.util.isArray)
1.  [function <span class="apidocSignatureSpan">json-mask.util.</span>isEmpty (obj)](#apidoc.element.json-mask.util.isEmpty)
1.  [function <span class="apidocSignatureSpan">json-mask.util.</span>isObject (obj)](#apidoc.element.json-mask.util.isObject)



# <a name="apidoc.module.json-mask"></a>[module json-mask](#apidoc.module.json-mask)

#### <a name="apidoc.element.json-mask.compile"></a>[function <span class="apidocSignatureSpan">json-mask.</span>compile (text)](#apidoc.element.json-mask.compile)
- description and source-code
```javascript
function compile(text) {
  if (!text) return null
  return parse(scan(text))
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.json-mask.filter"></a>[function <span class="apidocSignatureSpan">json-mask.</span>filter (obj, compiledMask)](#apidoc.element.json-mask.filter)
- description and source-code
```javascript
function filter(obj, compiledMask) {
  return util.isArray(obj)
    ? _arrayProperties(obj, compiledMask)
    : _properties(obj, compiledMask)
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.json-mask.util"></a>[module json-mask.util](#apidoc.module.json-mask.util)

#### <a name="apidoc.element.json-mask.util.has"></a>[function <span class="apidocSignatureSpan">json-mask.util.</span>has (obj, key)](#apidoc.element.json-mask.util.has)
- description and source-code
```javascript
function has(obj, key) {
  return ObjProto.hasOwnProperty.call(obj, key)
}
```
- example usage
```shell
...
var maskedObj, key, value, ret, retKey, typeFunc
if (!obj || !mask) return obj

if (util.isArray(obj)) maskedObj = []
else if (util.isObject(obj)) maskedObj = {}

for (key in mask) {
  if (!util.has(mask, key)) continue
  value = mask[key]
  ret = undefined
  typeFunc = (value.type === 'object') ? _object : _array
  if (key === '*') {
    ret = _forAll(obj, value.properties, typeFunc)
    for (retKey in ret) {
      if (!util.has(ret, retKey)) continue
...
```

#### <a name="apidoc.element.json-mask.util.isArray"></a>[function <span class="apidocSignatureSpan">json-mask.util.</span>isArray ()](#apidoc.element.json-mask.util.isArray)
- description and source-code
```javascript
function isArray() { [native code] }
```
- example usage
```shell
...


var util = require('./util')

module.exports = filter

function filter (obj, compiledMask) {
  return util.isArray(obj)
    ? _arrayProperties(obj, compiledMask)
    : _properties(obj, compiledMask)
}

// wrap array & mask in a temp object;
// extract results from temp at the end
function _arrayProperties (arr, mask) {
...
```

#### <a name="apidoc.element.json-mask.util.isEmpty"></a>[function <span class="apidocSignatureSpan">json-mask.util.</span>isEmpty (obj)](#apidoc.element.json-mask.util.isEmpty)
- description and source-code
```javascript
function isEmpty(obj) {
  if (obj == null) return true
  if (isArray(obj) ||
     (typeof obj === 'string')) return (obj.length === 0)
  for (var key in obj) if (has(obj, key)) return false
  return true
}
```
- example usage
```shell
...
  }

  return props
}

function _addToken (token, props) {
  props[token.value] = {type: token.type}
  if (!util.isEmpty(token.properties)) {
    props[token.value].properties = token.properties
  }
}
...
```

#### <a name="apidoc.element.json-mask.util.isObject"></a>[function <span class="apidocSignatureSpan">json-mask.util.</span>isObject (obj)](#apidoc.element.json-mask.util.isObject)
- description and source-code
```javascript
function isObject(obj) {
  return typeof obj === 'function' || typeof obj === 'object' && !!obj
}
```
- example usage
```shell
...
}

function _properties (obj, mask) {
var maskedObj, key, value, ret, retKey, typeFunc
if (!obj || !mask) return obj

if (util.isArray(obj)) maskedObj = []
else if (util.isObject(obj)) maskedObj = {}

for (key in mask) {
  if (!util.has(mask, key)) continue
  value = mask[key]
  ret = undefined
  typeFunc = (value.type === 'object') ? _object : _array
  if (key === '*') {
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

# api documentation for  [templar (v0.2.2)](https://github.com/isaacs/templar)  [![npm package](https://img.shields.io/npm/v/npmdoc-templar.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-templar) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-templar.svg)](https://travis-ci.org/npmdoc/node-npmdoc-templar)
#### A lightweight template thing

[![NPM](https://nodei.co/npm/templar.png?downloads=true)](https://www.npmjs.com/package/templar)

[![apidoc](https://npmdoc.github.io/node-npmdoc-templar/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-templar_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-templar/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-templar/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-templar/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Isaac Z. Schlueter",
        "email": "i@izs.me",
        "url": "http://blog.izs.me/"
    },
    "bugs": {
        "url": "https://github.com/isaacs/templar/issues"
    },
    "dependencies": {
        "lru-cache": "~2",
        "sigmund": "~1.0.0"
    },
    "description": "A lightweight template thing",
    "devDependencies": {
        "ejs": "~0.7.1",
        "request": "~2.11",
        "tap": "~0.2.4"
    },
    "directories": {},
    "dist": {
        "shasum": "0254f5770405b89041b7d4253ac897fdaea28518",
        "tarball": "https://registry.npmjs.org/templar/-/templar-0.2.2.tgz"
    },
    "homepage": "https://github.com/isaacs/templar",
    "license": "ISC",
    "main": "templar.js",
    "maintainers": [
        {
            "name": "isaacs",
            "email": "i@izs.me"
        }
    ],
    "name": "templar",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "url": "git://github.com/isaacs/templar.git"
    },
    "scripts": {
        "test": "tap test/*.js"
    },
    "version": "0.2.2"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module templar](#apidoc.module.templar)
1.  [function <span class="apidocSignatureSpan">templar.</span>loadFolder (folder)](#apidoc.element.templar.loadFolder)



# <a name="apidoc.module.templar"></a>[module templar](#apidoc.module.templar)

#### <a name="apidoc.element.templar.loadFolder"></a>[function <span class="apidocSignatureSpan">templar.</span>loadFolder (folder)](#apidoc.element.templar.loadFolder)
- description and source-code
```javascript
function loadFolder(folder) {
  loadFolder_(folder, templateCache, 0, 10)
  loaded[folder] = true
}
```
- example usage
```shell
...
'''javascript
var ejs = require('ejs')
, Templar = require('templar')
, templarOptions = { engine: ejs, folder: './templates' }

// preload it.  Otherwise, the first request is slow, because
// it has to load up all the templates within it.
Templar.loadFolder('./templates')

http.createServer(function (req, res) {
// note that this causes a sync fs hit the first time if
// the folder has not been loaded yet.
res.template = Templar(req, res, templarOptions)

// .. later, after figuring out which template to use ..
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

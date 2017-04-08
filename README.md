# api documentation for  [asar (v0.13.0)](https://github.com/electron/asar)  [![npm package](https://img.shields.io/npm/v/npmdoc-asar.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-asar) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-asar.svg)](https://travis-ci.org/npmdoc/node-npmdoc-asar)
#### Creating Electron app packages

[![NPM](https://nodei.co/npm/asar.png?downloads=true)](https://www.npmjs.com/package/asar)

[![apidoc](https://npmdoc.github.io/node-npmdoc-asar/build/screenCapture.buildNpmdoc.browser.%252Fhome%252Ftravis%252Fbuild%252Fnpmdoc%252Fnode-npmdoc-asar%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-asar/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-asar/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-asar/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "bin": {
        "asar": "./bin/asar.js"
    },
    "bugs": {
        "url": "https://github.com/electron/asar/issues"
    },
    "dependencies": {
        "chromium-pickle-js": "^0.2.0",
        "commander": "^2.9.0",
        "cuint": "^0.2.1",
        "glob": "^6.0.4",
        "minimatch": "^3.0.3",
        "mkdirp": "^0.5.0",
        "mksnapshot": "^0.3.0",
        "tmp": "0.0.28"
    },
    "description": "Creating Electron app packages",
    "devDependencies": {
        "lodash": "^4.2.1",
        "mocha": "^2.0.1",
        "rimraf": "^2.5.1",
        "standard": "^8.6.0"
    },
    "directories": {},
    "dist": {
        "shasum": "df33dd9d01bff842464d0d9f095740d4a62afb14",
        "tarball": "https://registry.npmjs.org/asar/-/asar-0.13.0.tgz"
    },
    "engines": {
        "node": ">=4.6"
    },
    "gitHead": "6034e128913818d90f5986000b39d28829340dd4",
    "homepage": "https://github.com/electron/asar",
    "license": "MIT",
    "main": "./lib/asar.js",
    "maintainers": [
        {
            "name": "atom",
            "email": "nathan@github.com"
        },
        {
            "name": "electron",
            "email": "electron@github.com"
        },
        {
            "name": "jlord",
            "email": "to.jlord@gmail.com"
        },
        {
            "name": "kevinsawicki",
            "email": "kevinsawicki@gmail.com"
        },
        {
            "name": "maxbrunsfeld",
            "email": "maxbrunsfeld@gmail.com"
        },
        {
            "name": "nathansobo",
            "email": "nathan@github.com"
        },
        {
            "name": "zcbenz",
            "email": "zcbenz@gmail.com"
        },
        {
            "name": "zeke",
            "email": "zeke@sikelianos.com"
        }
    ],
    "name": "asar",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/electron/asar.git"
    },
    "scripts": {
        "lint": "standard",
        "test": "mocha --reporter spec && npm run lint"
    },
    "standard": {
        "env": {
            "mocha": true
        }
    },
    "version": "0.13.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module asar](#apidoc.module.asar)
1.  [function <span class="apidocSignatureSpan">asar.</span>createPackage (src, dest, callback)](#apidoc.element.asar.createPackage)
1.  [function <span class="apidocSignatureSpan">asar.</span>createPackageFromFiles (src, dest, filenames, metadata, options, callback)](#apidoc.element.asar.createPackageFromFiles)
1.  [function <span class="apidocSignatureSpan">asar.</span>createPackageWithOptions (src, dest, options, callback)](#apidoc.element.asar.createPackageWithOptions)
1.  [function <span class="apidocSignatureSpan">asar.</span>extractAll (archive, dest)](#apidoc.element.asar.extractAll)
1.  [function <span class="apidocSignatureSpan">asar.</span>extractFile (archive, filename)](#apidoc.element.asar.extractFile)
1.  [function <span class="apidocSignatureSpan">asar.</span>listPackage (archive)](#apidoc.element.asar.listPackage)
1.  [function <span class="apidocSignatureSpan">asar.</span>statFile (archive, filename, followLinks)](#apidoc.element.asar.statFile)
1.  object <span class="apidocSignatureSpan">asar.</span>disk

#### [module asar.disk](#apidoc.module.asar.disk)
1.  [function <span class="apidocSignatureSpan">asar.disk.</span>readArchiveHeaderSync (archive)](#apidoc.element.asar.disk.readArchiveHeaderSync)
1.  [function <span class="apidocSignatureSpan">asar.disk.</span>readFileSync (filesystem, filename, info)](#apidoc.element.asar.disk.readFileSync)
1.  [function <span class="apidocSignatureSpan">asar.disk.</span>readFilesystemSync (archive)](#apidoc.element.asar.disk.readFilesystemSync)
1.  [function <span class="apidocSignatureSpan">asar.disk.</span>writeFilesystem (dest, filesystem, files, metadata, callback)](#apidoc.element.asar.disk.writeFilesystem)



# <a name="apidoc.module.asar"></a>[module asar](#apidoc.module.asar)

#### <a name="apidoc.element.asar.createPackage"></a>[function <span class="apidocSignatureSpan">asar.</span>createPackage (src, dest, callback)](#apidoc.element.asar.createPackage)
- description and source-code
```javascript
createPackage = function (src, dest, callback) {
  return module.exports.createPackageWithOptions(src, dest, {}, callback)
}
```
- example usage
```shell
...

'''js
var asar = require('asar');

var src = 'some/path/';
var dest = 'name.asar';

asar.createPackage(src, dest, function() {
  console.log('done.');
})
'''

Please note that there is currently **no** error handling provided!

### Transform
...
```

#### <a name="apidoc.element.asar.createPackageFromFiles"></a>[function <span class="apidocSignatureSpan">asar.</span>createPackageFromFiles (src, dest, filenames, metadata, options, callback)](#apidoc.element.asar.createPackageFromFiles)
- description and source-code
```javascript
createPackageFromFiles = function (src, dest, filenames, metadata, options, callback) {
  if (typeof metadata === 'undefined' || metadata === null) { metadata = {} }
  const filesystem = new Filesystem(src)
  const files = []
  const unpackDirs = []

  let filenamesSorted = []
  if (options.ordering) {
    const orderingFiles = fs.readFileSync(options.ordering).toString().split('\n').map(function (line) {
      if (line.includes(':')) { line = line.split(':').pop() }
      line = line.trim()
      if (line.startsWith('/')) { line = line.slice(1) }
      return line
    })

    const ordering = []
    for (const file of orderingFiles) {
      const pathComponents = file.split(path.sep)
      let str = src
      for (const pathComponent of pathComponents) {
        str = path.join(str, pathComponent)
        ordering.push(str)
      }
    }

    let missing = 0
    const total = filenames.length

    for (const file of ordering) {
      if (!filenamesSorted.includes(file) && filenames.includes(file)) {
        filenamesSorted.push(file)
      }
    }

    for (const file of filenames) {
      if (!filenamesSorted.includes(file)) {
        filenamesSorted.push(file)
        missing += 1
      }
    }

    console.log('Ordering file has ${((total - missing) / total) * 100}% coverage.')
  } else {
    filenamesSorted = filenames
  }

  const handleFile = function (filename, done) {
    let file = metadata[filename]
    let type
    if (!file) {
      const stat = fs.lstatSync(filename)
      if (stat.isDirectory()) { type = 'directory' }
      if (stat.isFile()) { type = 'file' }
      if (stat.isSymbolicLink()) { type = 'link' }
      file = {stat, type}
    }

    let shouldUnpack
    switch (file.type) {
      case 'directory':
        shouldUnpack = options.unpackDir
          ? isUnpackDir(path.relative(src, filename), options.unpackDir, unpackDirs)
          : false
        filesystem.insertDirectory(filename, shouldUnpack)
        break
      case 'file':
        shouldUnpack = false
        if (options.unpack) {
          shouldUnpack = minimatch(filename, options.unpack, {matchBase: true})
        }
        if (!shouldUnpack && options.unpackDir) {
          const dirName = path.relative(src, path.dirname(filename))
          shouldUnpack = isUnpackDir(dirName, options.unpackDir, unpackDirs)
        }
        files.push({filename: filename, unpack: shouldUnpack})
        filesystem.insertFile(filename, shouldUnpack, file, options, done)
        return
      case 'link':
        filesystem.insertLink(filename, file.stat)
        break
    }
    return process.nextTick(done)
  }

  const insertsDone = function () {
    return mkdirp(path.dirname(dest), function (error) {
      if (error) { return callback(error) }
      return disk.writeFilesystem(dest, filesystem, files, metadata, function (error) {
        if (error) { return callback(error) }
        if (options.snapshot) {
          return createSnapshot(src, dest, filenames, metadata, options, callback)
        } else {
          return callback(null)
        }
      })
    })
  }

  const names = filenamesSorted.slice()

  const next = function (name) {
    if (!name) { return insertsDone() }

    return handleFile(name, function () {
      return next(names.shift())
    })
  }

  return next(names.shift())
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.asar.createPackageWithOptions"></a>[function <span class="apidocSignatureSpan">asar.</span>createPackageWithOptions (src, dest, options, callback)](#apidoc.element.asar.createPackageWithOptions)
- description and source-code
```javascript
createPackageWithOptions = function (src, dest, options, callback) {
  const dot = typeof options.dot === 'undefined' ? true : options.dot

  return crawlFilesystem(src, { dot: dot }, function (error, filenames, metadata) {
    if (error) { return callback(error) }
    module.exports.createPackageFromFiles(src, dest, filenames, metadata, options, callback)
  })
}
```
- example usage
```shell
...
var src = 'some/path/';
var dest = 'name.asar';

function transform(filename) {
  return new CustomTransformStream()
}

asar.createPackageWithOptions(src, dest, { transform: transform }, function() {
  console.log('done.');
})
'''

## Using with grunt

There is also an unofficial grunt plugin to generate asar archives at [bwin/grunt-asar][grunt-asar].
...
```

#### <a name="apidoc.element.asar.extractAll"></a>[function <span class="apidocSignatureSpan">asar.</span>extractAll (archive, dest)](#apidoc.element.asar.extractAll)
- description and source-code
```javascript
extractAll = function (archive, dest) {
  const filesystem = disk.readFilesystemSync(archive)
  const filenames = filesystem.listFiles()

  // under windows just extract links as regular files
  const followLinks = process.platform === 'win32'

  // create destination directory
  mkdirp.sync(dest)

  return filenames.map((filename) => {
    filename = filename.substr(1)  // get rid of leading slash
    const destFilename = path.join(dest, filename)
    const file = filesystem.getFile(filename, followLinks)
    if (file.files) {
      // it's a directory, create it and continue with the next entry
      mkdirp.sync(destFilename)
    } else if (file.link) {
      // it's a symlink, create a symlink
      const linkSrcPath = path.dirname(path.join(dest, file.link))
      const linkDestPath = path.dirname(destFilename)
      const relativePath = path.relative(linkDestPath, linkSrcPath);
      // try to delete output file, because we can't overwrite a link
      (() => {
        try {
          fs.unlinkSync(destFilename)
        } catch (error) {}
      })()
      const linkTo = path.join(relativePath, path.basename(file.link))
      fs.symlinkSync(linkTo, destFilename)
    } else {
      // it's a file, extract it
      const content = disk.readFileSync(filesystem, filename, file)
      fs.writeFileSync(destFilename, content)
    }
  })
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.asar.extractFile"></a>[function <span class="apidocSignatureSpan">asar.</span>extractFile (archive, filename)](#apidoc.element.asar.extractFile)
- description and source-code
```javascript
extractFile = function (archive, filename) {
  const filesystem = disk.readFilesystemSync(archive)
  return disk.readFileSync(filesystem, filename, filesystem.getFile(filename))
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.asar.listPackage"></a>[function <span class="apidocSignatureSpan">asar.</span>listPackage (archive)](#apidoc.element.asar.listPackage)
- description and source-code
```javascript
listPackage = function (archive) {
  return disk.readFilesystemSync(archive).listFiles()
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.asar.statFile"></a>[function <span class="apidocSignatureSpan">asar.</span>statFile (archive, filename, followLinks)](#apidoc.element.asar.statFile)
- description and source-code
```javascript
statFile = function (archive, filename, followLinks) {
  const filesystem = disk.readFilesystemSync(archive)
  return filesystem.getFile(filename, followLinks)
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.asar.disk"></a>[module asar.disk](#apidoc.module.asar.disk)

#### <a name="apidoc.element.asar.disk.readArchiveHeaderSync"></a>[function <span class="apidocSignatureSpan">asar.disk.</span>readArchiveHeaderSync (archive)](#apidoc.element.asar.disk.readArchiveHeaderSync)
- description and source-code
```javascript
readArchiveHeaderSync = function (archive) {
  const fd = fs.openSync(archive, 'r')
  let size
  let headerBuf
  try {
    const sizeBuf = new Buffer(8)
    if (fs.readSync(fd, sizeBuf, 0, 8, null) !== 8) {
      throw new Error('Unable to read header size')
    }

    const sizePickle = pickle.createFromBuffer(sizeBuf)
    size = sizePickle.createIterator().readUInt32()
    headerBuf = new Buffer(size)
    if (fs.readSync(fd, headerBuf, 0, size, null) !== size) {
      throw new Error('Unable to read header')
    }
  } finally {
    fs.closeSync(fd)
  }

  const headerPickle = pickle.createFromBuffer(headerBuf)
  const header = headerPickle.createIterator().readString()
  return {header: JSON.parse(header), headerSize: size}
}
```
- example usage
```shell
...
  const headerPickle = pickle.createFromBuffer(headerBuf)
  const header = headerPickle.createIterator().readString()
  return {header: JSON.parse(header), headerSize: size}
}

module.exports.readFilesystemSync = function (archive) {
  if (!filesystemCache[archive]) {
    const header = this.readArchiveHeaderSync(archive)
    const filesystem = new Filesystem(archive)
    filesystem.header = header.header
    filesystem.headerSize = header.headerSize
    filesystemCache[archive] = filesystem
  }
  return filesystemCache[archive]
}
...
```

#### <a name="apidoc.element.asar.disk.readFileSync"></a>[function <span class="apidocSignatureSpan">asar.disk.</span>readFileSync (filesystem, filename, info)](#apidoc.element.asar.disk.readFileSync)
- description and source-code
```javascript
readFileSync = function (filesystem, filename, info) {
  let buffer = new Buffer(info.size)
  if (info.size <= 0) { return buffer }
  if (info.unpacked) {
    // it's an unpacked file, copy it.
    buffer = fs.readFileSync(path.join('${filesystem.src}.unpacked', filename))
  } else {
    // Node throws an exception when reading 0 bytes into a 0-size buffer,
    // so we short-circuit the read in this case.
    const fd = fs.openSync(filesystem.src, 'r')
    try {
      const offset = 8 + filesystem.headerSize + parseInt(info.offset)
      fs.readSync(fd, buffer, 0, info.size, offset)
    } finally {
      fs.closeSync(fd)
    }
  }
  return buffer
}
```
- example usage
```shell
...
const Filesystem = require('./filesystem')
const filesystemCache = {}

const copyFileToSync = function (dest, src, filename) {
const srcFile = path.join(src, filename)
const targetFile = path.join(dest, filename)

const content = fs.readFileSync(srcFile)
const stats = fs.statSync(srcFile)
mkdirp.sync(path.dirname(targetFile))
return fs.writeFileSync(targetFile, content, {mode: stats.mode})
}

const writeFileListToStream = function (dest, filesystem, out, list, metadata, callback) {
if (list.length === 0) {
...
```

#### <a name="apidoc.element.asar.disk.readFilesystemSync"></a>[function <span class="apidocSignatureSpan">asar.disk.</span>readFilesystemSync (archive)](#apidoc.element.asar.disk.readFilesystemSync)
- description and source-code
```javascript
readFilesystemSync = function (archive) {
  if (!filesystemCache[archive]) {
    const header = this.readArchiveHeaderSync(archive)
    const filesystem = new Filesystem(archive)
    filesystem.header = header.header
    filesystem.headerSize = header.headerSize
    filesystemCache[archive] = filesystem
  }
  return filesystemCache[archive]
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.asar.disk.writeFilesystem"></a>[function <span class="apidocSignatureSpan">asar.disk.</span>writeFilesystem (dest, filesystem, files, metadata, callback)](#apidoc.element.asar.disk.writeFilesystem)
- description and source-code
```javascript
writeFilesystem = function (dest, filesystem, files, metadata, callback) {
  let sizeBuf
  let headerBuf
  try {
    const headerPickle = pickle.createEmpty()
    headerPickle.writeString(JSON.stringify(filesystem.header))
    headerBuf = headerPickle.toBuffer()

    const sizePickle = pickle.createEmpty()
    sizePickle.writeUInt32(headerBuf.length)
    sizeBuf = sizePickle.toBuffer()
  } catch (error) {
    return callback(error)
  }

  const out = fs.createWriteStream(dest)
  out.on('error', callback)
  out.write(sizeBuf)
  return out.write(headerBuf, function () {
    return writeFileListToStream(dest, filesystem, out, files, metadata, callback)
  })
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

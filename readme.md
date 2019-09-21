# jsenv-import-map

[![npm package](https://img.shields.io/npm/v/@jsenv/import-map.svg)](https://www.npmjs.com/package/@jsenv/import-map)
[![ci status](https://github.com/jsenv/jsenv-import-map/workflows/ci/badge.svg)](https://github.com/jsenv/jsenv-import-map/actions)
[![codecov](https://codecov.io/gh/jsenv/jsenv-import-map/branch/master/graph/badge.svg)](https://codecov.io/gh/jsenv/jsenv-import-map)

> importMap programmatic implementation

## Introduction

`jsenv-import-map` implements importMap in native js. It is used by jsenv to use importMap even if they are not implemented by browsers.<br />
— see [importMap spec](https://github.com/WICG/import-maps)

It has the following exports

- `applyImportMap`
- `composeTwoImportMaps`
- `normalizeImportMap`
- `resolveImport`
- `resolveSpecifier`
- `wrapImportMap`

## resolveImport

> takes { specifier, importer, importMap, defaultExtension } and returns an url.

```js
import { resolveImport } from "@jsenv/import-map"

const importUrl = resolveImport({
  specifier: "../index.js",
  importer: "http://domain.com/folder/file.js",
  importMap: {
    imports: {
      "http://domain.com/index.js": "http://domain.com/main.js",
    },
  },
})

console.log(importUrl)
```

The code above logs `http://domain.com/main.js`.

## Installation

```console
npm install @jsenv/import-map@1.0.0
```

```console
yarn add @jsenv/import-map@1.0.0
```

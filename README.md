<div align="center">
  <img width="150" height="150" title="PostHTML" src="https://posthtml.github.io/posthtml/logo.svg">
  <h1>Plugin Starter Kit</h1>
  <p>A starter project for PostHTML plugins</p>

  [![Version][npm-version-shield]][npm]
  [![License][license-shield]][license]
  [![Build][travis-ci-shield]][travis-ci]
  [![Downloads][npm-stats-shield]][npm-stats]
</div>

## About

This is a starter project for PostHTML plugins.

Simply clone this repository, build your plugin, and update this readme.

```sh
git clone https://github.com/cossssmin/posthtml-plugin-starter.git
```

Features:

- Linting with [`xo`](https://github.com/xojs/xo) (opinionated config)
- Coverage report with [`nyc`](https://github.com/istanbuljs/nyc)
- Releases with [`np`](https://github.com/sindresorhus/np)
- Travis CI config
- Tests with [`ava`](https://github.com/avajs/ava)

---

## Introduction

Describe what your plugin does. 

Optionally add a short before & after example, like so:

Input:

```html
<div filter="uppercase">Test</div>
```

Output:

```html
<div>TEST</div>
```

## Install

```
$ npm i posthtml posthtml-myplugin
```

## Usage

Provide clear code samples showing how to use the plugin: 

```js
const fs = require('fs')
const posthtml = require('posthtml')
const myplugin = require('posthtml-myplugin')

const source = fs.readFileSync('./before.html')
// Source: <div filter="uppercase">Test</div>

posthtml([
    myplugin()
  ])
  .process(source)
  .then(result => fs.writeFileSync('./after.html', result.html))

  // Output: <div>TEST</div>
```

## Syntax

Many PostHTML plugins work off of custom HTML syntax that triggers them, like custom attributes or even custom tag names. If your plugin is triggered by custom markup, document it here.

For example:

### Attribute

You can use a filter by calling it inside a `filter` attribute:

```html
<div filter="uppercase">Test</div>
```

The `filter` attribute is removed in the output.

Result:

```html
<div>TEST</div>
```

### Tag

You can also use a `<filter>` tag, with a `name` attribute:

```html
<filter name="uppercase">Test</filter>
```

The tag is removed in the output.

Result:

```html
TEST
```


## Options

If you plugin can be configured through options, explain what they do and how to use them. Make sure to specify what the defaults are.

For example:

### `only`

Default: `[]`

Array of filter names to use. All other filters will be disabled.

By default, this is set to an empty array, which means that all filters can be used. 

## 3<sup>rd</sup> parties

If your plugin depends on third party libraries that require configuration, explain here what the user needs to do.

[npm]: https://www.npmjs.com/package/posthtml
[npm-version-shield]: https://img.shields.io/npm/v/posthtml.svg
[npm-stats]: http://npm-stat.com/charts.html?package=posthtml
[npm-stats-shield]: https://img.shields.io/npm/dt/posthtml.svg
[travis-ci]: https://travis-ci.org/posthtml/posthtml/
[travis-ci-shield]: https://img.shields.io/travis/posthtml/posthtml/master.svg
[license]: ./LICENSE
[license-shield]: https://img.shields.io/npm/l/posthtml.svg

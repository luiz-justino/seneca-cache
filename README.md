![Seneca](http://senecajs.org/files/assets/seneca-logo.png)
> A [Seneca.js][] plugin

# @seneca/cache

| ![Voxgig](https://www.voxgig.com/res/img/vgt01r.png) | This open source module is sponsored and supported by [Voxgig](https://www.voxgig.com). |
|---|---|

## Install

```sh
npm install seneca
npm install seneca-cache
```

### Quick example

This code snippet sets a value and then retrieves it.

```js
var seneca = require('seneca')();
seneca.use('cache');

seneca.ready(function(err) {
  seneca.act({role: 'cache', cmd: 'set', key: 'k1', val: 'v1'}, function(err) {
    seneca.act({role: 'cache', cmd: 'get', key: 'k1'}, function(err, out) {
      console.log('value = ' + out)
    });
  });
});
```


<!--START:options-->

## Quick Example

```js
require('seneca')()
  .use('seneca-cache')
```

## More Examples

See [test/](test/) for usage examples.

## Motivation

This module is a plugin for the [Seneca framework](http://senecajs.org). It provides a set of common caching actions (`get`, `set` etc.), backed by [lru-cache](https://github.com/isaacs/node-lru-cache).
It also exposes some lru-cache specific actions (`peek`, `has`, `keys`, `values`, `reset`).

By moving cache operations into Seneca, you can change your cache implementation or business rules at a later point.
For example, you might decide to send certain kinds of keys to a different cache mechanism, such as redis.

## Support

If you're using this module and need help, you can:

- Post a [github issue][]
- Tweet to [@senecajs][]

## API

### Options

* `micro.expiry` : number <i><small>11111</small></i>


Set plugin options when loading with:
```js


seneca.use('cache', { name: value, ... })


```


<small>Note: <code>foo.bar</code> in the list above means 
<code>{ foo: { bar: ... } }</code></small> 



<!--END:options-->

<!--START:action-list-->

### Action Patterns

* [role:cache,cmd:add](#-rolecachecmdadd-)
* [role:cache,cmd:clear](#-rolecachecmdclear-)
* [role:cache,cmd:decr](#-rolecachecmddecr-)
* [role:cache,cmd:delete](#-rolecachecmddelete-)
* [role:cache,cmd:get](#-rolecachecmdget-)
* [role:cache,cmd:incr](#-rolecachecmdincr-)
* [role:cache,cmd:micro](#-rolecachecmdmicro-)
* [role:cache,cmd:micro,get:stats](#-rolecachecmdmicrogetstats-)
* [role:cache,cmd:set](#-rolecachecmdset-)
* [role:cache,get:native](#-rolecachegetnative-)
* [role:lrucache,cmd:has](#-rolelrucachecmdhas-)
* [role:lrucache,cmd:keys](#-rolelrucachecmdkeys-)
* [role:lrucache,cmd:peek](#-rolelrucachecmdpeek-)
* [role:lrucache,cmd:reset](#-rolelrucachecmdreset-)
* [role:lrucache,cmd:values](#-rolelrucachecmdvalues-)


<!--END:action-list-->

<!--START:action-desc-->

## Contributing

The [Senecajs org][] encourages open participation. If you feel you can help in any way, be it with documentation, examples, extra testing, or new features please get in touch.

The [Senecajs org][] encourages open participation. If you feel you
can help in any way, be it with documentation, examples, extra
testing, or new features please get in touch.

### Running tests

```sh
npm run test
```

## Background

Implements the [Common Cache API](https://github.com/senecajs/seneca-cache/blob/main/README.md) for Seneca.

[![npm version][npm-badge]][npm-url]
[![Build Status][travis-badge]][travis-url]
[![Coverage Status][coveralls-badge]][coveralls-url]
[![Maintainability](https://api.codeclimate.com/v1/badges/9328019ed993fb5b1085/maintainability)](https://codeclimate.com/github/senecajs/seneca-cache/maintainability)
[![DeepScan grade](https://deepscan.io/api/teams/5016/projects/12815/branches/203961/badge/grade.svg)](https://deepscan.io/dashboard#view=project&tid=5016&pid=12815&bid=203961)
[![Dependency Status][david-badge]][david-url]
[![Gitter][gitter-badge]][gitter-url]
[MIT]: ./LICENSE
[Seneca.js]: https://www.npmjs.com/package/seneca
[travis-badge]: https://travis-ci.org/senecajs/seneca-cache.svg
[travis-url]: https://travis-ci.org/senecajs/seneca-cache
[npm-badge]: https://img.shields.io/npm/v/@seneca/cache.svg
[npm-url]: https://npmjs.com/package/@seneca/cache
[david-badge]: https://david-dm.org/senecajs/seneca-cache.svg
[david-url]: https://david-dm.org/senecajs/seneca-cache
[gitter-badge]: https://badges.gitter.im/Join%20Chat.svg
[gitter-url]: https://gitter.im/senecajs/seneca
[coveralls-badge]: https://coveralls.io/repos/github/senecajs/seneca-cache/badge.svg?branch=master
[coveralls-url]: https://coveralls.io/github/senecajs/seneca-cache?branch=master
[Senecajs org]: https://github.com/senecajs/

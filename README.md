# @dramaorg/repellat-nulla <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

ES Proposal spec-compliant shim for Set.prototype.difference. Invoke its "shim" method to shim `Set.prototype.difference` if it is unavailable or noncompliant.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES3-supported environment, and complies with the [proposed spec](https://github.com/tc39/proposal-set-methods). When shimmed, it uses [`es-set`](https://npmjs.com/es-set) to shim the `Set` implementation itself if needed.

Most common usage:
```js
var assert = require('assert');
var difference = require('@dramaorg/repellat-nulla');

var set1 = new Set([1, 2]);
var set2 = new Set([2, 3]);
var result = difference(set1, set2);

assert.deepEqual(result, new Set([1]));

difference.shim();

var shimmedResult = set1.difference(set2);
assert.deepEqual(shimmedResult, new Set([1]));
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

## Set Method Packages
 - [union](https://npmjs.com/set.prototype.union)
 - [intersection](https://npmjs.com/set.prototype.intersection)
 - [difference](https://npmjs.com/@dramaorg/repellat-nulla)
 - [symmetricDifference](https://npmjs.com/set.prototype.symmetricdifference)
 - [isSubsetOf](https://npmjs.com/set.prototype.issubsetof)
 - [isSupersetOf](https://npmjs.com/set.prototype.issupersetof)
 - [isDisjointFrom](https://npmjs.com/set.prototype.isdisjointfrom)

[package-url]: https://npmjs.com/package/@dramaorg/repellat-nulla
[npm-version-svg]: http://versionbadg.es/dramaorg/repellat-nulla.svg
[deps-svg]: https://david-dm.org/dramaorg/repellat-nulla.svg
[deps-url]: https://david-dm.org/dramaorg/repellat-nulla
[dev-deps-svg]: https://david-dm.org/dramaorg/repellat-nulla/dev-status.svg
[dev-deps-url]: https://david-dm.org/dramaorg/repellat-nulla#info=devDependencies
[testling-svg]: https://ci.testling.com/dramaorg/repellat-nulla.png
[testling-url]: https://ci.testling.com/dramaorg/repellat-nulla
[npm-badge-png]: https://nodei.co/npm/@dramaorg/repellat-nulla.png?downloads=true&stars=true
[license-image]: http://img.shields.io/npm/l/@dramaorg/repellat-nulla.svg
[license-url]: LICENSE
[downloads-image]: http://img.shields.io/npm/dm/@dramaorg/repellat-nulla.svg
[downloads-url]: http://npm-stat.com/charts.html?package=@dramaorg/repellat-nulla
[codecov-image]: https://codecov.io/gh/dramaorg/repellat-nulla/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/dramaorg/repellat-nulla/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/dramaorg/repellat-nulla
[actions-url]: https://github.com/dramaorg/repellat-nulla/actions

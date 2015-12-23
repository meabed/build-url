# build-url

[![Build Status](https://travis-ci.org/steverydz/build-url.svg?branch=master)](https://travis-ci.org/steverydz/build-url)

A library that builds a URL, including it's path, query parameters and fragment identifier. Works in node and in the browser.

## Installation

To install with bower:
```
bower install build-url --save
```

To install with npm:

```
npm install build-url --save
```

## Usage

Usage in the browser:

```
<script src="../path/to/lib/build-url.js"></script>
<script>
buildUrl('http://example.com', {
  path: 'about',
  hash: 'contact',
  queryParams: {
    foo: bar,
    bar: ['foo', 'bar']
  }
});
</script>
```

Usage with ES6 modules:
```
import buildUrl from '../path/to/lib/build-url';

buildUrl('http://example.com', {
  path: 'about',
  hash: 'contact',
  queryParams: {
    foo: bar,
    bar: ['foo', 'bar']
  }
});
```

Usage with node:

```
var buildUrl = require('build-url');

buildUrl('http://example.com', {
  path: 'about',
  hash: 'contact',
  queryParams: {
    foo: bar,
    bar: ['foo', 'bar']
  }
});
```

## Options

The `buildUrl` function accepts two arguments. The first is a URL e.g. `http://example.com`. The second is an object where you can specify the `path`, `hash`, and an object of `queryParams`:

```
buildUrl('http://example.com', {
  path: 'about'
  hash: 'contact',
  queryParams: {
    foo: 'bar',
    bar: 'baz'
  }
});

// returns http://example.com/about?foo=bar&bar=baz#contact
```

If you pass an array to the `queryParams` object, it will be transformed to a comma separated list:

```
buildUrl('http://example.com', {
  queryParams: {
    foo: 'bar',
    bar: ['one', 'two', 'three']
  }
});

// returns http://example.com?foo=bar&bar=one,two,three
```

## License

This is licensed under an MIT License. [See details](LICENSE)

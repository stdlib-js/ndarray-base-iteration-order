<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# Iteration Order

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Given a stride array, determine array iteration order.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->



<section class="usage">

## Usage

```javascript
import iterationOrder from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-base-iteration-order@deno/mod.js';
```

#### iterationOrder( strides )

Returns the array iteration order.

```javascript
var o = iterationOrder( [ 2, 1 ] );
// returns 1

o = iterationOrder( [ -2, 1 ] );
// returns 0

o = iterationOrder( [ -2, -1 ] );
// returns -1
```

The function returns one of the following values:

-   `0`: unordered (strides are of mixed sign).
-   `1`: left-to-right iteration order (strides are all nonnegative).
-   `-1`: right-to-left iteration order (strides are all negative).

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
import discreteUniform from 'https://cdn.jsdelivr.net/gh/stdlib-js/random-base-discrete-uniform@deno/mod.js';
import shape2strides from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-base-shape2strides@deno/mod.js';
import randu from 'https://cdn.jsdelivr.net/gh/stdlib-js/random-base-randu@deno/mod.js';
import iterationOrder from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-base-iteration-order@deno/mod.js';

var strides;
var shape;
var out;
var i;
var j;

shape = [ 0, 0, 0 ];
shape[ 0 ] = discreteUniform( 1, 10 );
shape[ 1 ] = discreteUniform( 1, 10 );
shape[ 2 ] = discreteUniform( 1, 10 );

strides = shape2strides( shape, 'row-major' );

for ( i = 0; i < 100; i++ ) {
    j = discreteUniform( 0, shape.length-1 );
    strides[ j ] *= ( randu() < 0.5 ) ? -1 : 1;
    out = iterationOrder( strides );
    console.log( 'strides: %s => %d', strides.join( ',' ), out );
}
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2024. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/ndarray-base-iteration-order.svg
[npm-url]: https://npmjs.org/package/@stdlib/ndarray-base-iteration-order

[test-image]: https://github.com/stdlib-js/ndarray-base-iteration-order/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/ndarray-base-iteration-order/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/ndarray-base-iteration-order/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/ndarray-base-iteration-order?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/ndarray-base-iteration-order.svg
[dependencies-url]: https://david-dm.org/stdlib-js/ndarray-base-iteration-order/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/ndarray-base-iteration-order/tree/deno
[umd-url]: https://github.com/stdlib-js/ndarray-base-iteration-order/tree/umd
[esm-url]: https://github.com/stdlib-js/ndarray-base-iteration-order/tree/esm
[branches-url]: https://github.com/stdlib-js/ndarray-base-iteration-order/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/ndarray-base-iteration-order/main/LICENSE

</section>

<!-- /.links -->

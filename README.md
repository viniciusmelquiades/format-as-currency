# format-as-currency

[![Build Status][build]](https://circleci.com/gh/bcherny/format-as-currency) [![Coverage Status][coverage]](https://coveralls.io/r/bcherny/format-as-currency) ![][bower] [![npm]](https://www.npmjs.com/package/format-as-currency) [![cc0]](http://creativecommons.org/about/cc0)

[build]: https://img.shields.io/circleci/project/bcherny/format-as-currency.svg?branch=master&style=flat-square
[coverage]: http://img.shields.io/coveralls/bcherny/format-as-currency.svg?branch=master&style=flat-square
[bower]: https://img.shields.io/bower/v/format-as-currency.svg?style=flat-square
[npm]: https://img.shields.io/npm/v/format-as-currency.svg?style=flat-square
[cc0]: https://img.shields.io/npm/l/format-as-currency.svg?style=flat-square

Angular directive to format an input as a currency as the user types. Like [autoNumeric](https://github.com/BobKnothe/autoNumeric) for Angular.

## Demo

http://bcherny.github.io/format-as-currency/demo

## Installation

Install via bower or NPM:

- Bower: `bower install --save format-as-currency`
- NPM: `npm install --save format-as-currency`

## Usage

```html
<div ng-controller="myController">
  <input
    format-as-currency
    ng-model="value"
    type="text"
  >
</div>

<script src="bower_components/angular/angular.js"></script>
<script src="bower_components/format-as-currency/format-as-currency.js"></script>
<script>
  angular
  .module('myModule', [
    'bcherny/formatAsCurrency'
  ])
  .controller('myController', function ($scope) {
    $scope.value = '' // currency input value
  })
</script>
```

### With a custom curency formatter

```html
<input
  format-as-currency
  currency-filter="'myFilter'"
  ng-model="value"
  type="text"
>
<script>
  angular
  ...
  .filter('myFilter', function () {
    return function (value) {
      return '¥' + value
    }
  })
</script>
```

# Running the tests

```sh
npm test
```
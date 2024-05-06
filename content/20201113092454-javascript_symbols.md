---
id: 1e9f826e-69c6-4a52-8cf8-135abc082fb3
title: JavaScript Symbols
---

-   [JavaScript Symbol Prototype
    Methods](20201116101443-javascript_symbol_prototype_methods)

# Description

These are tokens that serve as unique IDs. You create symbols via the
factory function `Symbol()` (which is loosely similar to
[string](20200922164551-strings) returning strings if called as a
function).

# Syntax

``` javascript
const symbol1 = Symbol();
```

## Add a description

``` javascript
const tralala = Symbol('tralala')
console.log(tralala) // Symbol(tralala)
```

## Convert to string

``` javascript
const tralala = Symbol('tralala')
console.log(String(tralala)) // `Symbol(tralala)`
```

## Every Symbol is unique

``` javascript
console.log(Symbol() === Symbol()) // false
```

## Property keys

``` javascript
const KEY = Symbol();
const obj = {};

obj[KEY] = 123;
console.log(obj[KEY]); // 123
```

``` javascript
const FOO = Symbol();
const obj = {
    [FOO]() {
        return 'bar';
    }
};
console.log(obj[FOO]()); // bar
```

# Use as reserved inherited method names

If for some bizarre reason you want to use reserved inherited method
names yourself (like toString) you can with Symbols.

``` javascript
const toStringSymbol = Symbol("toString");
Array.prototype[toStringSymbol] = function() {
  return `${this.length} cm of blue yarn`;
};

console.log([1, 2].toString()); //1, 2
console.log([1, 2][toStringSymbol]()); // 2 cm of blue yarn
```

# Expressions

Symbols can also be used in [object](20200826201605-objects) expressions
and [classes](20201008090316-class_notation).

``` javascript
const toStringSymbol = Symbol("toString");

let stringObject = {
  [toStringSymbol]() {
    return "a jute rope";
  },
};
console.log(stringObject[toStringSymbol]()); // a jute rope
```

---
publish: true
title: JavaScript Symbols
created: 2020-11-13T09:24:54
modified: 2026-08-12T09:44:58.338Z
---

# JavaScript Symbols

- [[JavaScript Symbol Prototype Methods]]

## Description

These are tokens that serve as unique IDs. You create symbols via the factory function ~Symbol()~ (which is loosely similar to [[JavaScript Strings]] returning strings if called as a function).

## Syntax

```js
const symbol1 = Symbol();
```

### Add a description

```js
const tralala = Symbol('tralala')
console.log(tralala) // Symbol(tralala)
```

### Convert to string

```js
const tralala = Symbol('tralala')
console.log(String(tralala)) // `Symbol(tralala)`
```

### Every Symbol is unique

```js
console.log(Symbol() === Symbol()) // false
```

### Property keys

```js
const KEY = Symbol();
const obj = {};

obj[KEY] = 123;
console.log(obj[KEY]); // 123
```

```js
const FOO = Symbol();
const obj = {
    [FOO]() {
        return 'bar';
    }
};
console.log(obj[FOO]()); // bar
```

## Use as reserved inherited method names

If for some bizarre reason you want to use reserved inherited method names yourself (like toString) you can with Symbols.

```js
const toStringSymbol = Symbol("toString");
Array.prototype[toStringSymbol] = function() {
  return `${this.length} cm of blue yarn`;
};

console.log([1, 2].toString()); //1, 2
console.log([1, 2][toStringSymbol]()); // 2 cm of blue yarn
```

## Expressions

Symbols can also be used in [[JavaScript Objects]] expressions and [[JavaScript Class Notation]].

```js
const toStringSymbol = Symbol("toString");

let stringObject = {
  [toStringSymbol]() {
    return "a jute rope";
  },
};
console.log(stringObject[toStringSymbol]()); // a jute rope
```

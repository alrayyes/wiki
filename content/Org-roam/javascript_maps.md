---
publish: true
title: JavaScript Maps
created: 2020-10-12T09:37:45
modified: 2026-08-05T07:58:56.690Z
---

# JavaScript Maps

# Description

For sane people [ES6](ES6) comes with a +half assed "solution"+ handy data structure called ~Map~ which prevents the diy shenanigans below.

# Syntax

## Basic operation

### Single entries

```js
const map = new Map();
const KEY = {};

map.set(KEY, 123);
console.log(map.get(KEY)); // 123

console.log(map.has(KEY)); // true

map.delete(KEY);
console.log(map.has(KEY)); // false
```

### Array

```js
const map = new Map([
    [ 1, 'one' ],
    [ 2, 'two' ],
    [ 3, 'three' ],
]);
```

## Iteration

### Keys

```js
const map = new Map([
    [false, 'no'],
    [true,  'yes'],
]);

for (const key of map.keys()) {
    console.log(key);
}
```

### Values

```js
const map = new Map([
    [false, 'no'],
    [true,  'yes'],
]);

for (const value of map.values()) {
    console.log(value);
}
```

### Entries

```js
const map = new Map([
  [false, "no"],
  [true, "yes"],
]);

for (const entry of map.entries()) {
  console.log(entry[0], entry[1]);
}
```

### Converting to Arrays

The [Spread (...)](Spread "...") operator (...) can turn an \[JavaScript Iterables]\(JavaScript Iterables) into an \[JavaScript Arrays]\(JavaScript Arrays)

```js
const map = new Map().set(false, 'no').set(true, 'yes');
console.log([...map.keys()]) // false, true
```

```js
const map = new Map().set(false, 'no').set(true, 'yes');
console.log([...map])
```

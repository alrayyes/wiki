---
publish: true
title: JavaScript Number library
created: 2020-09-23T15:34:25
modified: 2026-08-12T09:44:58.333Z
---

# JavaScript Number library

## ES6

### .EPSILON

Compares floating point numbers with a tolerance for rounding errors.

### .isInteger(num)

```js
  console.log(Number.isInteger(1.05)) // false
  console.log(Number.isInteger(1)) // true
  console.log(Number.isInteger(-3.1)) // false
  console.log(Number.isInteger(-3)) // true
```

### .isNaN

Checks whether num is the value NaN. In contrast to the global function isNaN(), it doesn’t coerce its argument to a number and is therefore safer for non-numbers:

```js
console.log(isNaN('???')) // true
console.log(Number.isNaN('???')) // false
```

### .isFinite

Determines whether the passed value is a finite number

```js
console.log(Number.isFinite(Infinity)) // false
console.log(Number.isFinite(123)) // true
```

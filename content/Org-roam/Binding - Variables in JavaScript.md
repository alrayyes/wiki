---
publish: true
aliases:
  - Binding / Variables in JavaScript
title: Binding / Variables in JavaScript
created: 2020-06-13T17:21:37
---

## ES6

### Let

```js
let caught = 5 * 5
console.log(caught)

let mood = "light"
console.log(mood)
mood = "dark"
console.log(mood)

let luigisDebt = 140;
luigisDebt = luigisDebt - 35;
console.log(luigisDebt);
```

A single let statement my define multiple bindings

```js
let one = 1, two = 2
console.log(one + two)
```

### Const

This is a constant binding. It points to the same value for as long as it lives

```js
const blaat = "abcd"
console.log(blaat)
/**
 * Following will both cause errors:
 *
 * blaat = "efgh"
 * let blaat = "efgh"
*/
```

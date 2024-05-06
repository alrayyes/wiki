---
id: 6efc70be-8154-420f-a92e-622ef1ad960c
title: Binding / Variables in JavaScript
---

# ES6

## Let

``` javascript
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

``` javascript
let one = 1, two = 2
console.log(one + two)
```

## Const

This is a constant binding. It points to the same value for as long as
it lives

``` javascript
const blaat = "abcd"
console.log(blaat)
/**
 * Following will both cause errors:
 *
 * blaat = "efgh"
 * let blaat = "efgh"
*/
```

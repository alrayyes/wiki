---
publish: true
title: Array.prototype.Sort()
created: 2020-11-16T15:54:59
modified: 2026-08-12T10:31:55.387Z
---

# Array.prototype.Sort()

## Description

Sorts array

## Syntax

```js
const months = ['March', 'Jan', 'Feb', 'Dec'];
months.sort();
console.log(months); // ["Dec", "Feb", "Jan", "March"]

const array1 = [1, 30, 4, 21, 100000];
array1.sort();
console.log(array1); // [1, 100000, 21, 30, 4]
```

## Changes

[[.sort() is guaranteed to be stable]]

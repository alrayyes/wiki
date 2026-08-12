---
publish: true
title: Array.prototype.map()
created: 2020-11-13T11:31:41
modified: 2026-08-12T10:26:13.157Z
---

# Array.prototype.map()

## Description

\~map()~ creates a new array populated with the results of calling a passed function on every element in the calling array.

## Syntax

```js
const array = [1, 2, 3, 4];
const map1 = array.map((x) => x * 2);

console.log(map1); // [(2, 4, 6, 8)]
```

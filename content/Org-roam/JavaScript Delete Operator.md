---
publish: true
title: JavaScript Delete Operator
created: 2020-11-13T09:46:52
modified: 2026-08-12T10:26:13.177Z
---

# JavaScript Delete Operator

## Description

The ~delete~ operator deletes a binding (duh).

## Syntax

```js
let anObject = { left: 1, right: 2 };
console.log(anObject.left); // 1

delete anObject.left;

console.log(anObject.left); // undefined
console.log("left" in anObject); // false
console.log("right" in anObject); // true
```

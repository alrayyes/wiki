---
id: aed94d48-374c-4f3d-8dca-b6e4b3f9ae83
title: JavaScript Delete Operator
---

# Description

The `delete` operator deletes a binding (duh).

# Syntax

``` javascript
let anObject = { left: 1, right: 2 };
console.log(anObject.left); // 1

delete anObject.left;

console.log(anObject.left); // undefined
console.log("left" in anObject); // false
console.log("right" in anObject); // true
```

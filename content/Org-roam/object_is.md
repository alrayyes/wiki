---
publish: true
title: Object.is
created: 2020-11-13T09:53:00
modified: 2026-08-05T10:26:50.510Z
---

# Object.is

# Description

\~Object.is~ provides a way of comparing values that's more precise than ~===~

```js
console.log(NaN === NaN) // false
console.log(Object.is(NaN, NaN)) //true
console.log(-0 === +0) // true
console.log(Object.is(-0, +0)) // false
```

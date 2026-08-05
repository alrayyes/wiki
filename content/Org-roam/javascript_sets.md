---
publish: true
title: JavaScript Sets
created: 2020-10-12T09:42:48
modified: 2026-08-05T07:58:56.692Z
---

# JavaScript Sets

- [Introduction](#introduction)
- [Example](#example)

# Introduction

A \[\[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Set]\[Set]] is a collection of unique elements.

# Example

```js
const arr = [5, 1, 5, 7, 7, 5];
const unique = [...new Set(arr)]; // [ 5, 1, 7 ]
```

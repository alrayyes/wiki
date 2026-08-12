---
publish: true
title: JavaScript Sets
created: 2020-10-12T09:42:48
---

## Introduction

A [Set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set) is a collection of unique elements.

## Example

```js
const arr = [5, 1, 5, 7, 7, 5];
const unique = [...new Set(arr)]; // [ 5, 1, 7 ]
```

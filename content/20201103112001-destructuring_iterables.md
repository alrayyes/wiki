---
id: 96e9e4f6-8d7d-4a46-85ef-7cb3eb3804df
title: Destructuring Iterables
---

# Introduction

This was introduced in [ES6](20201030093404-es6). Destructuring
[iterables](20201014092625-javascript_iterables) works on the same
principle as [arrays](20201103111509-destructuring_arrays).

# Syntax

``` javascript
const [x,...y] = 'abc'
console.log(x, y) // a ['b', 'c']
```

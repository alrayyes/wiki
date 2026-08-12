---
publish: true
title: Destructuring Iterables
created: 2020-11-03T11:20:01
---

# Destructuring Iterables

## Introduction

This was introduced in [[ES6]]. Destructuring [[JavaScript Iterables]] works on the same principle as [[Destructuring Arrays]].

## Syntax

```js
const [x,...y] = 'abc'
console.log(x, y) // a ['b', 'c']
```

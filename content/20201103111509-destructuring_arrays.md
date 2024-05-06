---
id: 05066fdd-18fe-4762-b836-af35ba1f625b
title: Destructuring Arrays
---

# Introduction

Destructuring [arrays](20200826201029-arrays) was introduced in
[ES6](20201030093404-es6).
[Iterables](20201103112001-destructuring_iterables) can also be
destructured via the same principle.

# Syntax

``` javascript
const [, year, month, day] =
    /^(\d\d\d\d)-(\d\d)-(\d\d)$/
    .exec('2999-12-31');

console.log(`${year} ${month} ${day}`) // 2999 12 31
```

---
publish: true
title: Destructuring Arrays
created: 2020-11-03T11:15:09
modified: 2026-08-12T09:44:58.319Z
---

# Destructuring Arrays

## Introduction

Destructuring [[JavaScript Arrays]] was introduced in [[ES6]]. [[Destructuring Iterables]] can also be destructured via the same principle.

## Syntax

```js
const [, year, month, day] =
    /^(\d\d\d\d)-(\d\d)-(\d\d)$/
    .exec('2999-12-31');

console.log(`${year} ${month} ${day}`) // 2999 12 31
```

---
publish: true
title: Destructuring Arrays
created: 2020-11-03T11:15:09
modified: 2026-08-05T07:58:56.678Z
---

# Destructuring Arrays

- [Introduction](#introduction)
- [Syntax](#syntax)

# Introduction

Destructuring \[JavaScript Arrays]\(JavaScript Arrays) was introduced in [ES6](ES6). \[Destructuring Iterables]\(Destructuring Iterables) can also be destructured via the same principle.

# Syntax

```js
const [, year, month, day] =
    /^(\d\d\d\d)-(\d\d)-(\d\d)$/
    .exec('2999-12-31');

console.log(`${year} ${month} ${day}`) // 2999 12 31
```

---
publish: true
title: Destructuring Objects
created: 2020-11-03T11:17:46
modified: 2026-08-05T10:26:50.498Z
---

# Destructuring Objects

- [Introduction](#introduction)
- [Syntax](#syntax)

# Introduction

Destructuring \[JavaScript Objects]\(JavaScript Objects) introduced in [ES6](ES6). \[Rest Operator (...) in Object Destructuring]\(Rest Operator (...) in Object Destructuring) can also be used here.

# Syntax

```js
const saviour = { first: "Jonn", last: "Connor" };
const { f, l } = saviour;

console.log(saviour, f, l); // { first: 'John', last: 'Connor' } John Connor
```

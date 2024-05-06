---
id: b817ea12-eeeb-4723-a90c-f016cdcdb866
title: Destructuring Objects
---

# Introduction

Destructuring [objects](20200826201605-objects) introduced in
[ES6](20201030093404-es6). [Rest
Operator](20201103111357-rest_operator_in_object_destructuring) can also
be used here.

# Syntax

``` javascript
const saviour = { first: "Jonn", last: "Connor" };
const { f, l } = saviour;

console.log(saviour, f, l); // { first: 'John', last: 'Connor' } John Connor
```

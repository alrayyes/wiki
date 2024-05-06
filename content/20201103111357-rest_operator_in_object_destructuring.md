---
id: 78ef5b06-a541-4e33-9c51-af92cd91719c
title: Rest Operator (…) in Object Destructuring
---

# Introduction

Introduced in [ES2018](20201030095105-es2018) to help with
[destructuring](20200922160850-destructuring).

# Syntax

## Basic

``` javascript
const obj = { foo: 1, bar: 2, baz: 3 };
const { foo, ...rest } = obj;

console.log(foo); // 1
console.log(rest); // { bar: 2, baz: 3 }
```

## Named parameters

The rest operator can also be used with [named
parameters](20200922162127-named_parameters):

``` javascript
function func({ param1, param2, ...rest }) {
  // rest operator
  console.log("All parameters: ", { param1, param2, ...rest }); // spread operator
  return param1 + param2;
}
```

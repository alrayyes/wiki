---
publish: true
title: Rest Operator (...) in Object Destructuring
created: 2020-11-03T11:13:57
modified: 2026-08-05T10:26:50.514Z
---

# Rest Operator (...) in Object Destructuring

# Introduction

Introduced in [ES2018](ES2018) to help with \[JavaScript Destructuring]\(JavaScript Destructuring).

# Syntax

## Basic

const obj = { foo: 1, bar: 2, baz: 3 };
const { foo, ...rest } = obj;

console.log(foo); // 1
console.log(rest); // { bar: 2, baz: 3 }

## Named parameters

The rest operator can also be used with \[JavaScript Named parameters]\(JavaScript Named parameters):

function func({ param1, param2, ...rest }) {
// rest operator
console.log("All parameters: ", { param1, param2, ...rest }); // spread operator
return param1 + param2;
}

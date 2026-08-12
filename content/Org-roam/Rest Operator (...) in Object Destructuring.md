---
publish: true
title: Rest Operator (...) in Object Destructuring
created: 2020-11-03T11:13:57
---

## Introduction

Introduced in [[ES2018]] to help with [[JavaScript Destructuring]].

## Syntax

### Basic

```js
const obj = { foo: 1, bar: 2, baz: 3 };
const { foo, ...rest } = obj;

console.log(foo); // 1
console.log(rest); // { bar: 2, baz: 3 }
```

### Named parameters

The rest operator can also be used with [[JavaScript Named parameters]]:

```js
function func({ param1, param2, ...rest }) {
  // rest operator
  console.log("All parameters: ", { param1, param2, ...rest }); // spread operator
  return param1 + param2;
}
```

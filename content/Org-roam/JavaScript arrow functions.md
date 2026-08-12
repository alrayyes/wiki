---
publish: true
title: JavaScript arrow functions
created: 2020-10-06T11:13:49
modified: 2026-08-12T09:32:15.611Z
---

# JavaScript arrow functions

## Introduction

```js
const power = (base, exponent) => {
  let result = 1;
  for (let count = 0; count < exponent; count++) {
    result *= base;
  }
  return result;
};

console.log(power(2, 3))
```

If there is only one parameter name, parentheses can be omitted around the parameter list. Same for the function body and brackets

```js
const square1 = (x) => { return x * x; };
const square2 = x => x * x;

console.log(square1(5))
console.log(square1(6))
```

When an arrow function has no parameters at all, its parameter is just an empty set of parentheses

```js
const horn = () => {
  console.log("Toot");
};

horn()
```

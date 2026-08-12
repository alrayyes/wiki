---
publish: true
title: Recursion in JavaScript
created: 2020-07-02T20:44:37
modified: 2026-08-12T10:26:13.196Z
---

# Recursion in JavaScript

```js
function power(base, exponent) {
  if (exponent == 0) {
    return 1;
  } else {
    return base * power(base, exponent - 1);
  }
}

console.log(power(2, 3));
```

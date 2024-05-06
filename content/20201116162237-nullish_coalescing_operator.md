---
id: 64df7704-1f31-4da6-95f3-2747a031fbf9
title: Nullish coalescing operator (??)
---

# Description

Returns right-hand side operand when it's left-hand side operand is
`null` or `undefined`, and otherwise returns its left-hand side operand.

# Syntax

``` javascript
const foo = null ?? 'default string';
console.log(foo); // default string

const baz = 0 ?? 42;
console.log(baz); // 0
```

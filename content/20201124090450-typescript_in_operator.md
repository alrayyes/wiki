---
id: c8b933ca-82db-4fff-a679-943133513d6e
title: TypeScript in Operator
---

# Description

The `in` operator returns true if the specifiec property is in the
specified object.

# Syntax

``` typescript
interface A {
  x: number;
}
interface B {
  y: string;
}
​
function doStuff(q: A | B) {
  if ('x' in q) {
    // q: A
  }
  else {
    // q: B
  }
}
```

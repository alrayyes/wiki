---
publish: true
title: TypeScript in Operator
created: 2020-11-24T09:04:50
---

## Description

The ~in~ operator returns true if the specifiec property is in the specified object.

## Syntax

```typescript
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

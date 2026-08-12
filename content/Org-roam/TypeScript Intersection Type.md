---
publish: true
title: TypeScript Intersection Type
created: 2020-09-29T16:33:16
modified: 2026-08-12T10:26:13.212Z
---

# TypeScript Intersection Type

## Description

\~extend~ is a very common pattern in [[JavaScript]] where you take two [[JavaScript Objects]] and create a new one that has the features of both these objects. An ~Intersection Type~ allows you to use this pattern in a safe way.

## Syntax

```typescript
function extend<T, U>(first: T, second: U): T & U {
  return { ...first, ...second };
}

const x = extend({ a: "hello" }, { b: 42 });

// x now has both `a` and `b`
const a = x.a;
const b = x.b;
```

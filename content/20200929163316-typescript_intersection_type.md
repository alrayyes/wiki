---
id: e3434ce4-0210-4a9b-92ed-9da1e5000bac
title: TypeScript Intersection Type
---

# Description

`extend` is a very common pattern in
[JavaScript](20200613170905-javascript) where you take two
[objects](20200826201605-objects) and create a new one that has the
features of both these objects. An `Intersection Type` allows you to use
this pattern in a safe way.

# Syntax

``` typescript
function extend<T, U>(first: T, second: U): T & U {
  return { ...first, ...second };
}

const x = extend({ a: "hello" }, { b: 42 });

// x now has both `a` and `b`
const a = x.a;
const b = x.b;
```

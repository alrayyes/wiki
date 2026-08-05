---
publish: true
title: Closure in JavaScript
created: 2020-07-02T20:43:51
modified: 2026-08-05T07:58:56.674Z
---

# Closure in JavaScript

Local bindings are created anew for every call, and different calls can't affect on another calls local bindings.

```js
function wrapValue(n) {
  let local = n;
  return () => local;
}

let wrap1 = wrapValue(1);
let wrap2 = wrapValue(2);
console.log(wrap1());
console.log(wrap2());
```

A function that references bindings from local scopes around it is called a closure. This behavior not only frees you from having to worry about lifetimes of bindings but also makes it possible to use function values in some creative ways.

```js
function multiplier(factor) {
  return number => number * factor;
}

let twice = multiplier(2);

console.log(twice(5));
```

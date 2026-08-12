---
publish: true
title: Object.fromEntries
created: 2020-11-16T09:51:24
modified: 2026-08-12T10:31:55.419Z
---

# Object.fromEntries

## Given an [[JavaScript Iterables]] over \[key,value] pairs, ~Object.fromEntries()~ creates an object. It does the opposite of [[Object.entries]]. See the proposal[^proposal] for more information.

## Syntax

```js
console.log(
  Object.fromEntries([
    ["foo", 1],
    ["bar", 2],
  ])
); // { foo: 1, bar: 2 }
```

## Footnotes

[^proposal]: https://github.com/tc39/proposal-object-from-entries

---
publish: true
title: Array.from()
created: 2020-11-13T10:58:32
modified: 2026-08-12T10:26:13.156Z
---

# Array.from()

## Syntax

```js
const arr2 = Array.from(arguments);
```

If a value is [[JavaScript Iterables]] (as all Array-like DOM data structure are by now), you can also use the [[Spread (...)]] operator (...) to convert it to an [[JavaScript Arrays]]:

```js
const arr1 = [...'abc'];
    // ['a', 'b', 'c']
const arr2 = [...new Set().add('a').add('b')];
    // ['a', 'b']
```

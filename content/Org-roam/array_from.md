---
publish: true
title: Array.from()
created: 2020-11-13T10:58:32
modified: 2026-08-05T07:58:56.670Z
---

# Array.from()

# Syntax

```js
const arr2 = Array.from(arguments);
```

If a value is \[JavaScript Iterables]\(JavaScript Iterables) (as all Array-like DOM data structure are by now), you can also use the [Spread (...)](Spread "...") operator (...) to convert it to an \[JavaScript Arrays]\(JavaScript Arrays):

```js
const arr1 = [...'abc'];
    // ['a', 'b', 'c']
const arr2 = [...new Set().add('a').add('b')];
    // ['a', 'b']
```

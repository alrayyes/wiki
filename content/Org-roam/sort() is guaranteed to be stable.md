---
publish: true
aliases:
  - .sort() is guaranteed to be stable
title: .sort() is guaranteed to be stable
created: 2020-11-16T15:58:10
---

# .sort() is guaranteed to be stable

## Description

If elements that are considered equal by sorting then sorting does not change the order of those elements.

## Example

```js
const arr = [
  { key: "b", value: 1 },
  { key: "a", value: 2 },
  { key: "b", value: 3 },
];
arr.sort((x, y) => x.key.localeCompare(y.key, "en-US"));
console.log(arr); // [ { key: 'a', value: 1 }, { key: 'b', value: 1 }, { key: 'b', value: 3 } ]
```

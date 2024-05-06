---
id: 15a17612-7b15-4d40-9294-caa6d1e4fe1a
title: .sort() is guaranteed to be stable
---

# Description

If elements that are considered equal by sorting then sorting does not
change the order of those elements.

# Example

``` javascript
const arr = [
  { key: "b", value: 1 },
  { key: "a", value: 2 },
  { key: "b", value: 3 },
];
arr.sort((x, y) => x.key.localeCompare(y.key, "en-US"));
console.log(arr); // [ { key: 'a', value: 1 }, { key: 'b', value: 1 }, { key: 'b', value: 3 } ]
```

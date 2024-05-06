---
id: 87eebd15-af30-482c-83be-d9f77ecf83d0
title: Object.fromEntries
---

# Given an [iterable](20201014092625-javascript_iterables) over \[key,value\] pairs, `Object.fromEntries()` creates an object. It does the opposite of [Object.entries](20201113102048-object_entries). See the proposal[^1] for more information.

# Syntax

``` javascript
console.log(
  Object.fromEntries([
    ["foo", 1],
    ["bar", 2],
  ])
); // { foo: 1, bar: 2 }
```

# Footnotes

[^1]: <https://github.com/tc39/proposal-object-from-entries>

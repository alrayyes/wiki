---
publish: true
title: .sort() is guaranteed to be stable
created: 2020-11-16T15:58:10
modified: 2026-08-05T07:58:56.710Z
---

# .sort() is guaranteed to be stable

# Description

If elements that are considered equal by sorting then sorting does not change the order of those elements.

# Example

const arr = \[
{ key: "b", value: 1 },
{ key: "a", value: 2 },
{ key: "b", value: 3 },
];
arr.sort((x, y) => x.key.localeCompare(y.key, "en-US"));
console.log(arr); // \[ { key: 'a', value: 1 }, { key: 'b', value: 1 }, { key: 'b', value: 3 } ]

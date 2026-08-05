---
publish: true
title: Object.entries
created: 2020-11-13T10:20:48
modified: 2026-08-05T10:26:50.510Z
---

# Object.entries

# Description

Returns \[JavaScript Objects]\(JavaScript Objects) properties as key / value pairs. Can be used with \[JavaScript Maps]\(JavaScript Maps) as well. It does the opposite of [Object.fromEntries](Object.fromEntries).

# Syntax

```js
console.log(Object.entries({ one: 1, two: 2 })); // [['one', 1], ['two', 2]]
```

## Maps

```js
let map = new Map(
  Object.entries({
    one: 1,
    two: 2,
  })
);
console.log(JSON.stringify([...map])); // [["one", 1], ["two", 2]]
```

---
publish: true
title: Object.entries
created: 2020-11-13T10:20:48
---

## Description

Returns [[JavaScript Objects]] properties as key / value pairs. Can be used with [[JavaScript Maps]] as well. It does the opposite of [[Object.fromEntries]].

## Syntax

```js
console.log(Object.entries({ one: 1, two: 2 })); // [['one', 1], ['two', 2]]
```

### Maps

```js
let map = new Map(
  Object.entries({
    one: 1,
    two: 2,
  })
);
console.log(JSON.stringify([...map])); // [["one", 1], ["two", 2]]
```

---
publish: true
title: JavaScript For Of
created: 2020-10-30T09:33:04
modified: 2026-08-12T10:31:55.408Z
---

# JavaScript For Of

## Syntax

```js
const arr = ['a', 'b', 'c'];
for (const elem of arr) {
    console.log(elem);
}
```

```js
const arr = ["a", "b", "c"];
for (const [index, elem] of arr.entries()) {
  console.log(index + ". " + elem);
}
```

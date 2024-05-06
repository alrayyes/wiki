---
id: 88c7d978-30a1-4908-bbd8-3263fb6c1d44
title: JavaScript For Of
---

# Syntax

``` javascript
const arr = ['a', 'b', 'c'];
for (const elem of arr) {
    console.log(elem);
}
```

``` javascript
const arr = ["a", "b", "c"];
for (const [index, elem] of arr.entries()) {
  console.log(index + ". " + elem);
}
```

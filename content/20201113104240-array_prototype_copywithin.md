---
id: 5b058b90-1a05-4c2f-a64a-a56d3c768191
title: Array.prototype.copyWithin()
---

# Description

This copies the elements whose indices are in the range \[start,end) to
index target and subsequent indices. If the two index ranges overlap,
care is taken that all source elements are copied before they are
overwritten. I am confused as to how this is in any way useful.

# Syntax

``` typescript
Array.prototype.copyWithin(target : number,
    start : number, end = this.length) : This
```

``` javascript
const arr = [0,1,2,3];
console.log(arr.copyWithin(2, 0, 2)) // [0, 1, 0, 1]
```

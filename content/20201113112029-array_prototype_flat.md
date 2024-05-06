---
id: caa62af1-768f-4ca7-95c2-ba38c703101d
title: Array.prototype.flat()
---

# Description

Flattens an [array](20200826201029-arrays).

# Type Signature

``` typescript
.flat(depth = 1): any[]
```

# Syntax

``` javascript
console.log([1, 2, [3, 4], [[5, 6]]].flat(0)); // [ 1, 2, [ 3, 4 ], [ [ 5, 6 ] ] ]
console.log([1, 2, [3, 4], [[5, 6]]].flat(1)); // [ 1, 2, 3, 4, [ 5, 6 ] ]
console.log([1, 2, [3, 4], [[5, 6]]].flat(2)); // [ 1, 2, 3, 4, 5, 6 ]
```

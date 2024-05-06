---
id: 1aa59b86-bbea-4eb7-beac-67c7e1460ecf
title: Array.prototype.flatMap()
---

# Description

Is the same as calling [JavaScript Maps](20201012093745-javascript_maps)
and then flattening the result. Ie:

``` javascript
arr.map(func).flat(1)
```

# Type Signature

``` typescript
.flatMap<U>(
  callback: (value: T, index: number, array: T[]) => U|Array<U>,
  thisValue?: any
): U[]
```

# Syntax

``` javascript
console.log(["a", "b", "c"].flatMap((x) => x)); // [ 'a', 'b', 'c' ]
console.log(["a", "b", "c"].flatMap((x) => [x])); // [ 'a', 'b', 'c' ]
console.log(["a", "b", "c"].flatMap((x) => [[x]])); // [ [ 'a' ], [ 'b' ], [ 'c' ] ]
console.log(["a", "b", "c"].flatMap((x, i) => new Array(i + 1).fill(x))); // [ 'a', 'b', 'b', 'c', 'c', 'c' ]
```

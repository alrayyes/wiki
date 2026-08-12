---
publish: true
title: Array.prototype.flatMap()
created: 2020-11-13T11:20:58
modified: 2026-08-12T10:26:13.157Z
---

# Array.prototype.flatMap()

## Description

Is the same as calling [[JavaScript Maps]] and then flattening the result. Ie:

```js
arr.map(func).flat(1)
```

## Type Signature

```typescript
.flatMap<U>(
  callback: (value: T, index: number, array: T[]) => U|Array<U>,
  thisValue?: any
): U[]
```

## Syntax

```js
console.log(["a", "b", "c"].flatMap((x) => x)); // [ 'a', 'b', 'c' ]
console.log(["a", "b", "c"].flatMap((x) => [x])); // [ 'a', 'b', 'c' ]
console.log(["a", "b", "c"].flatMap((x) => [[x]])); // [ [ 'a' ], [ 'b' ], [ 'c' ] ]
console.log(["a", "b", "c"].flatMap((x, i) => new Array(i + 1).fill(x))); // [ 'a', 'b', 'b', 'c', 'c', 'c' ]
```

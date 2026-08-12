---
publish: true
title: Array.prototype.flat()
created: 2020-11-13T11:20:29
modified: 2026-08-12T10:26:13.157Z
---

# Array.prototype.flat()

## Description

Flattens an [[JavaScript Arrays]].

## Type Signature

```typescript
.flat(depth = 1): any[]
```

## Syntax

```js
console.log([1, 2, [3, 4], [[5, 6]]].flat(0)); // [ 1, 2, [ 3, 4 ], [ [ 5, 6 ] ] ]
console.log([1, 2, [3, 4], [[5, 6]]].flat(1)); // [ 1, 2, 3, 4, [ 5, 6 ] ]
console.log([1, 2, [3, 4], [[5, 6]]].flat(2)); // [ 1, 2, 3, 4, 5, 6 ]
```

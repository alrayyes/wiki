---
publish: true
title: TypeScript Arrays
created: 2020-09-29T16:21:29
modified: 2026-08-05T10:26:50.494Z
---

# TypeScript Arrays

# Syntax

```typescript
var boolArray: boolean[];

boolArray = [true, false];
console.log(boolArray[0]); // true
console.log(boolArray.length); // 2
boolArray[1] = true;
boolArray = [false, false];

boolArray[0] = 'false'; // Error!
boolArray = 'false'; // Error!
boolArray = [true, 'false']; // Error!
```

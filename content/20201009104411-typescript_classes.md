---
id: b6fa7fa7-644f-42ab-bee6-71f4f58a60f2
title: TypeScript Classes
---

# TypeScript 4.0

## Class Property Inference from Constructors

TypeScript 4.0 can now use control flow analysis to determine the types
of properties in [classes](20201008090316-class_notation) when
noImplicitAny is enabled.

``` typescript
class Square {
    // Previously: implicit any!
    // Now: inferred to `number`!
    area;
    sideLength;

    constructor(sideLength: number) {
        this.sideLength = sideLength;
        this.area = sideLength ** 2;
    }
}
```

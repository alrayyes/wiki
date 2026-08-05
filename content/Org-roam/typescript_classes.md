---
publish: true
title: TypeScript Classes
created: 2020-10-09T10:44:11
modified: 2026-08-05T10:26:50.520Z
---

# TypeScript Classes

- [TypeScript 4.0](#typescript-40)
  - [Class Property Inference from Constructors](#class-property-inference-from-constructors)

# TypeScript 4.0

## Class Property Inference from Constructors

TypeScript 4.0 can now use control flow analysis to determine the types of properties in \[JavaScript Class Notation]\(JavaScript Class Notation) when noImplicitAny is enabled.

```typescript
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

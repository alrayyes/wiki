---
publish: true
title: TypeScript Interfaces
created: 2020-09-29T16:22:20
modified: 2026-08-12T09:44:58.362Z
---

# TypeScript Interfaces

## Example

```typescript
interface Name {
    first: string;
    second: string;
}

var name: Name;
name = {
    first: 'John',
    second: 'Doe'
};

name = {           // Error : `second` is missing
    first: 'John'
};
name = {           // Error : `second` is the wrong type
    first: 'John',
    second: 1337
};
```

### Class implementing interface

```typescript
interface Point {
    x: number; y: number;
}

class MyPoint implements Point {
    x: number; y: number; // Same as Point
}
```

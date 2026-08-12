---
publish: true
title: TypeScript Inline Type Annotation
created: 2020-09-29T16:24:17
modified: 2026-08-12T09:44:58.362Z
---

# TypeScript Inline Type Annotation

## Syntax

```typescript
var name: {
    first: string;
    second: string;
};
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

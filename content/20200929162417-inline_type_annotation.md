---
id: 01e5c8e4-5227-4565-96e5-94a4bb6240ea
title: TypeScript Inline Type Annotation
---

# Syntax

``` typescript
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

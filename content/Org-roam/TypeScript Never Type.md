---
publish: true
title: TypeScript Never Type
created: 2020-10-07T09:56:14
---

## Introduction

[[TypeScript]] supports bottom types[^bottomtypes]. Cases where this occurs:

- A function never returns (e.g. if the function body has src\_js{while(true){}})
- A function always throws (src\_js{function foo(){throw new Error('Not Implemented')}})

## Syntax

```typescript
let foo: never; // Okay
```

```typescript
let foo: never = 123; // Error: Type number is not assignable to never

// Okay as the function's return type is `never`
let bar: never = (() => { throw new Error(`Throw my hands in the air like I just don't care`) })();
```

## Footnotes

[^bottomtypes]: https://en.wikipedia.org/wiki/Bottom_type

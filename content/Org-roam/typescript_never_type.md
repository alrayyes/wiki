---
publish: true
title: TypeScript Never Type
created: 2020-10-07T09:56:14
modified: 2026-08-05T07:58:56.719Z
---

# TypeScript Never Type

- [Introduction](#introduction)
- [Syntax](#syntax)
- [Footnotes](#footnotes)

# Introduction

[TypeScript](TypeScript) supports bottom types\[fn:bottomtypes]. Cases where this occurs:

- A function never returns (e.g. if the function body has src\_js{while(true){}})
- A function always throws (src\_js{function foo(){throw new Error('Not Implemented')}})

# Syntax

```typescript
let foo: never; // Okay
```

```typescript
let foo: never = 123; // Error: Type number is not assignable to never

// Okay as the function's return type is `never`
let bar: never = (() => { throw new Error(`Throw my hands in the air like I just don't care`) })();
```

# Footnotes

\[fn:bottomtypes]https://en.wikipedia.org/wiki/Bottom\_type

---
id: 85c2204d-dc1e-4038-9355-8bed1cb4574b
title: TypeScript Never Type
---

# Introduction

[TypeScript](20200929161126-typescript) supports bottom types[^1]. Cases
where this occurs:

-   A function never returns (e.g. if the function body has
    `while(true){`})
-   A function always throws
    (`function foo(){throw new Error('Not Implemented')`})

# Syntax

``` typescript
let foo: never; // Okay
```

``` typescript
let foo: never = 123; // Error: Type number is not assignable to never

// Okay as the function's return type is `never`
let bar: never = (() => { throw new Error(`Throw my hands in the air like I just don't care`) })();
```

# Footnotes

[^1]: <https://en.wikipedia.org/wiki/Bottom_type>

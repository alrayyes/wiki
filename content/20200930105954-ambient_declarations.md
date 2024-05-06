---
id: e1048c95-3baa-445e-a943-bff7b86a0f29
title: Ambient Declarations
---

# Introduction

Ambient declarations allow you to safely use existing popular JavaScript
libraries and incrementally migrate your
JavaScript/CoffeeScript/Other-Compile-To-Js-Language project to
TypeScript.

# Declaration Files

Syntax is simple:

``` typescript
declare var foo: any
```

Declarations can be put in a `.ts` or `.d.ts` file, ie: `global.d.ts` or
`vendor.d.ts`

# Best Practices

-   Use `.d.ts`
-   Use [interfaces](20200929162220-interfaces) where possible

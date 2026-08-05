---
publish: true
title: Ambient Declarations
created: 2020-09-30T10:59:54
modified: 2026-08-05T07:58:56.669Z
---

# Ambient Declarations

- [Introduction](#introduction)
- [Declaration Files](#declaration-files)
- [Best Practices](#best-practices)

# Introduction

Ambient declarations allow you to safely use existing popular JavaScript libraries and incrementally migrate your JavaScript/CoffeeScript/Other-Compile-To-Js-Language project to TypeScript.

# Declaration Files

Syntax is simple:

```typescript
declare var foo: any
```

Declarations can be put in a ~.ts~ or ~.d.ts~ file, ie: ~global.d.ts~ or ~vendor.d.ts~

# Best Practices

- Use ~.d.ts~
- Use \[TypeScript Interfaces]\(TypeScript Interfaces) where possible

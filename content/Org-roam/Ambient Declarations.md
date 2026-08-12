---
publish: true
title: Ambient Declarations
created: 2020-09-30T10:59:54
modified: 2026-08-12T10:31:55.385Z
---

# Ambient Declarations

## Introduction

Ambient declarations allow you to safely use existing popular JavaScript libraries and incrementally migrate your JavaScript/CoffeeScript/Other-Compile-To-Js-Language project to TypeScript.

## Declaration Files

Syntax is simple:

```typescript
declare var foo: any
```

Declarations can be put in a ~.ts~ or ~.d.ts~ file, ie: ~global.d.ts~ or ~vendor.d.ts~

## Best Practices

- Use ~.d.ts~
- Use [[TypeScript Interfaces]] where possible

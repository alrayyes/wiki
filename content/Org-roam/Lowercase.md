---
publish: true
title: Lowercase
created: 2020-11-23T10:33:15
modified: 2026-08-12T09:32:15.623Z
---

# Lowercase

## Description

Transforms every string character to lowercase for [[TypeScript Template Literal String Type]].

## Syntax

```typescript
type UnenthusiasticGreeting<T extends string> = `${Lowercase<T>}`

type HELLO = UnenthusiasticGreeting<"HELLO">;
// same as
//   type HELLO = "hello";
```

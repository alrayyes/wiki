---
publish: true
title: Uppercase
created: 2020-11-23T10:32:50
modified: 2026-08-12T10:26:13.214Z
---

# Uppercase

## Description

Transforms every string character to uppercase for [[TypeScript Template Literal String Type]].

## Syntax

```typescript
type EnthusiasticGreeting<T extends string> = `${Uppercase<T>}`

type HELLO = EnthusiasticGreeting<"hello">;
// same as
//   type HELLO = "HELLO";
```

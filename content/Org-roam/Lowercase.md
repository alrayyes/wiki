---
publish: true
title: Lowercase
created: 2020-11-23T10:33:15
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

---
publish: true
title: Capitalize
created: 2020-11-23T10:33:33
---

# Capitalize

## Description

Transforms the first string character to uppercase for [[TypeScript Template Literal String Type]].

## Syntax

```typescript
type CapitalizedGreeting<T extends string> = `${Capitalize<T>}`

type HELLO = CapitalizedGreeting<"hello">;
// same as
//   type HELLO = "Hello";
```

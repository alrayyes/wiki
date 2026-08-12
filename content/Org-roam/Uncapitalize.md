---
publish: true
title: Uncapitalize
created: 2020-11-23T10:34:00
---

# Uncapitalize

## Description

Transforms the first string character to lowercase for [[TypeScript Template Literal String Type]].

## Syntax

```typescript
type UncapitalizedGreeting<T extends string> = `${Uncapitalize<T>}`

type HELLO = CapitalizedGreeting<"Hello">;
// same as
//   type HELLO = "hello";
```

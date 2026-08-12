---
publish: true
title: TypeScript strictNullChecks
created: 2020-11-24T09:15:30
modified: 2026-08-12T09:32:15.642Z
---

# TypeScript strictNullChecks

## Description

Check if variable is null

## Syntax

```typescript
function foo(a?: number | null) {
  if (a == null) return;

  // a is number now.
}
```

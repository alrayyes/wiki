---
id: 40929849-a8dc-4293-8e24-afa2ff04620d
title: TypeScript strictNullChecks
---

# Description

Check if variable is null

# Syntax

``` typescript
function foo(a?: number | null) {
  if (a == null) return;

  // a is number now.
}
```

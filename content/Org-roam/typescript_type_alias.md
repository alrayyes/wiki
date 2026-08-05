---
publish: true
title: TypeScript Type Alias
created: 2020-09-29T16:38:25
modified: 2026-08-05T07:58:56.719Z
---

# TypeScript Type Alias

# Description

The make your own Sundae of Types.

# Sytax

```typescript
type StrOrNum = string|number;

// Usage: just like any other notation
var sample: StrOrNum;
sample = 123;
sample = '123';

// Just checking
sample = true; // Error!
```

```typescript
type Text = string | { text: string };
type Coordinates = [number, number];
type Callback = (data: string) => void;
```

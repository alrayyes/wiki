---
id: 188e8fe7-0f96-4b05-97f2-fc2a760ccab4
title: TypeScript Type Alias
---

# Description

The make your own Sundae of Types.

# Sytax

``` typescript
type StrOrNum = string|number;

// Usage: just like any other notation
var sample: StrOrNum;
sample = 123;
sample = '123';

// Just checking
sample = true; // Error!
```

``` typescript
type Text = string | { text: string };
type Coordinates = [number, number];
type Callback = (data: string) => void;
```

---
publish: true
aliases:
  - Optional Chaining Operator (?.)
title: Optional Chaining Operator (?.)
created: 2020-11-16T16:26:28
modified: 2026-08-12T09:44:58.343Z
---

# Optional Chaining Operator (?.)

## Description

Permits reading the value of a property located within a chain of connected objects without having to expressly validate that each reference in the chain is valid.

## Syntax

```js
const adventurer = {
  name: "Alice",
  cat: {
    name: "Dinah",
  },
};

const dogName = adventurer.dog?.name;
console.log(dogName); // undefined

console.log(adventurer.someNonExistentMethod?.()); // undefined
```

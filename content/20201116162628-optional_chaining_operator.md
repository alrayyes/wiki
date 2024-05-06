---
id: 653df156-531e-48c9-a637-a1609069ff8e
title: Optional Chaining Operator (?.)
---

# Description

Permits reading the value of a property located within a chain of
connected objects without having to expressly validate that each
reference in the chain is valid.

# Syntax

``` javascript
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

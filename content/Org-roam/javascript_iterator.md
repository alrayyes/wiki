---
publish: true
title: JavaScript Iterator
created: 2020-10-14T09:28:46
modified: 2026-08-05T10:26:50.505Z
---

# JavaScript Iterator

- [Introduction](#introduction)
- [Examples](#examples)
  - [Syntax](#syntax)
  - [TypeScript Interfaces](#typescript-interfaces)

# Introduction

An /iterator/ is a pointer for traversing the elements of a data structure.

# Examples

## Syntax

const iterable = \["a", "b"];
const iterator = iterable[Symbol.iterator]();

console.log(iterator.next()); // { value: 'a', done: false }
console.log(iterator.next()); // { value: 'b', done: false }
console.log(iterator.next()); // { value: undefined, done: true }

## TypeScript Interfaces

Expressed as \[TypeScript Interfaces]\(TypeScript Interfaces) in [TypeScript](TypeScript) notation:

```typescript
interface Iterable {
    [Symbol.iterator]() : Iterator;
}
interface Iterator {
    next() : IteratorResult;
}
interface IteratorResult {
    value: any;
    done: boolean;
}
```

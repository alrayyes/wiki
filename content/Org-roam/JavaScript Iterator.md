---
publish: true
title: JavaScript Iterator
created: 2020-10-14T09:28:46
---

# JavaScript Iterator

## Introduction

An /iterator/ is a pointer for traversing the elements of a data structure.

## Examples

### Syntax

```js
const iterable = ["a", "b"];
const iterator = iterable[Symbol.iterator]();

console.log(iterator.next()); // { value: 'a', done: false }
console.log(iterator.next()); // { value: 'b', done: false }
console.log(iterator.next()); // { value: undefined, done: true }
```

### TypeScript Interfaces

Expressed as [[TypeScript Interfaces]] in [[TypeScript]] notation:

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

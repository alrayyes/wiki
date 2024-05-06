---
id: 9f77a5b0-a06d-46d0-828e-d6c5fe33111d
title: JavaScript Iterator
---

# Introduction

An *iterator* is a pointer for traversing the elements of a data
structure.

# Examples

## Syntax

``` javascript
const iterable = ["a", "b"];
const iterator = iterable[Symbol.iterator]();

console.log(iterator.next()); // { value: 'a', done: false }
console.log(iterator.next()); // { value: 'b', done: false }
console.log(iterator.next()); // { value: undefined, done: true }
```

## TypeScript Interfaces

Expressed as [interfaces](20200929162220-interfaces) in
[TypeScript](20200929161126-typescript) notation:

``` typescript
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

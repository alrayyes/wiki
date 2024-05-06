---
id: 6383dfcd-c925-4d33-8338-2da22edf7ef8
title: Object.getOwnPropertyDescriptors
---

# Description

Returns property descriptors of all known properties of an
[object](20200826201605-objects).

# Syntax

``` javascript
const obj = {
  [Symbol("foo")]: 123,
  get bar() {
    return "abc";
  },
};
console.log(Object.getOwnPropertyDescriptors(obj));

// Output:
// { [Symbol('foo')]:
//    { value: 123,
//      writable: true,
//      enumerable: true,
//      configurable: true },
//   bar:
//    { get: [Function: bar],
//      set: undefined,
//      enumerable: true,
//      configurable: true } }
```

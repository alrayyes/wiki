---
publish: true
title: Object.getOwnPropertyDescriptors
created: 2020-11-13T10:21:25
modified: 2026-08-12T10:26:13.190Z
---

# Object.getOwnPropertyDescriptors

## Description

Returns property descriptors of all known properties of an [[JavaScript Objects]].

## Syntax

```js
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

```
{
  bar: {
    get: [Function: get bar],
    set: undefined,
    enumerable: true,
    configurable: true
  },
  [Symbol(foo)]: { value: 123, writable: true, enumerable: true, configurable: true }
}
undefined
```

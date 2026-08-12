---
publish: true
title: JavaScript For Await Of
created: 2020-10-30T09:57:41
modified: 2026-08-12T10:26:13.178Z
---

# JavaScript For Await Of

## Syntax

```js
async function f() {
  for await (const x of createAsyncIterable(["a", "b"])) {
    console.log(x);
  }
}
// Output:
// a
// b
```

## Rejections

Like ~await~ in [[JavaScript Async Functions]], th eloop throws an exception if ~next()~ returns a rejection:

```js
function createRejectingIterable() {
  return {
    [Symbol.asyncIterator]() {
      return this;
    },
    next() {
      return Promise.reject(new Error("Problem!"));
    },
  };
}
(async function () {
  // (A)
  try {
    for await (const x of createRejectingIterable()) {
      console.log(x);
    }
  } catch (e) {
    console.error(e);
    // Error: Problem!
  }
})(); // (B)
```

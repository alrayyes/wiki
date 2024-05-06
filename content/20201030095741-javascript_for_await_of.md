---
id: 3dac2b04-4015-4c1f-847c-5e677aec1fc0
title: JavaScript For Await Of
---

# Syntax

``` javascript
async function f() {
  for await (const x of createAsyncIterable(["a", "b"])) {
    console.log(x);
  }
}
// Output:
// a
// b
```

# Rejections

Like `await` in [async
functions](20201026103714-javascript_async_functions), th eloop throws
an exception if `next()` returns a rejection:

``` javascript
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

---
id: fc8cc294-ab54-44cb-8a3a-f18036ffe175
title: JavaScript Async Iterator
---

# Syntax

``` javascript
async function* createAsyncIterable(syncIterable) {
  for (const elem of syncIterable) {
    yield elem;
  }
}

const asyncIterable = createAsyncIterable(["a", "b"]);
const asyncIterator = asyncIterable[Symbol.asyncIterator]();
asyncIterator
  .next()
  .then((iterResult1) => {
    console.log(iterResult1);
    return asyncIterator.next();
    // { value: 'a', done: false }
  })
  .then((iterResult2) => {
    console.log(iterResult2);
    return asyncIterator.next();
    // { value: 'b', done: false }
  })
  .then((iterResult3) => {
    console.log(iterResult3);
    // { value: undefined, done: true }
  });
```

# TypeScript interfaces

The [interfaces](20200929162220-interfaces), in
[TypeScript](20200929161126-typescript) notation:

``` typescript
interface AsyncIterable {
  [Symbol.asyncIterator](): AsyncIterator;
}
interface AsyncIterator {
  next(): Promise<IteratorResult>;
}
interface IteratorResult {
  value: any;
  done: boolean;
}
```

# See also

-   [Generators](20200911155947-generators)
-   [For Await Of](20201030095741-javascript_for_await_of)

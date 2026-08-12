---
publish: true
title: JavaScript Async Iterator
created: 2020-10-30T09:22:00
---

## Syntax

```js
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

## TypeScript interfaces

The [[TypeScript Interfaces]], in [[TypeScript]] notation:

```typescript
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

## See also

- [[JavaScript Generators]]
- [[JavaScript For Await Of]]

---
publish: true
title: JavaScript Async Functions
created: 2020-10-26T10:37:14
modified: 2026-08-12T10:31:55.405Z
---

# JavaScript Async Functions

## Introduction

Async Functions[^async-functions] is a new feature implemented in [[ES2017]] to handle [[JavaScript Promises]].

## Syntax

### Fulfilling a promise

```js
async function asyncFunc() {
  return 123;
}

asyncFunc().then((x) => console.log(x));
// 123
```

### Rejecting a promise

```js
async function asyncFunc() {
  throw new Error("Problem!");
}

asyncFunc().catch((err) => console.log(err));
// Error: Problem!
```

## Footnotes

[^async-functions]: https://github.com/tc39/ecmascript-asyncawait

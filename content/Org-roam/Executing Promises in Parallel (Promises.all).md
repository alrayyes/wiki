---
publish: true
title: Executing Promises in Parallel (Promises.all)
created: 2020-11-11T09:49:57
---

# Executing Promises in Parallel (Promises.all)

## Description

Run promises in parallel. Will throw an [[JavaScript Exceptions]] if one of the requests fail.

## Syntax

```js
Promise.all([
    asyncFunc1(),
    asyncFunc2(),
])
.then(([result1, result2]) => {
})
.catch(err => {
    // Receives first rejection among the Promises
});
```

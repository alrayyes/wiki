---
publish: true
title: Executing Promises in Parallel
created: 2020-11-11T09:49:57
modified: 2026-08-12T09:32:15.603Z
---

# Executing Promises in Parallel

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

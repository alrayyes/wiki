---
publish: true
title: Executing Promises in Parallel
created: 2020-11-11T09:49:57
---

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

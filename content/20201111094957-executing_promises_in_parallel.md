---
id: 9c42715a-8324-4570-ab92-927b608aa02a
title: Executing Promises in Parallel
---

``` javascript
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

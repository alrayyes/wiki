---
id: fe95210e-f59a-45a4-b0ed-f4d3ec981a07
title: Executing Promises in Parallel (Promises.all)
---

# Description

Run promises in parallel. Will throw an
[exception](20201111092905-javascript_exceptions) if one of the requests
fail.

# Syntax

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

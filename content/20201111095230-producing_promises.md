---
id: e059aba7-2912-4a54-8c04-dbb6fbd3d0a7
title: Producing Promises
---

# Advice

Use [Async functions](20201026103714-javascript_async_functions) instead
of this.

# Syntax

``` javascript
const p = new Promise(
    function (resolve, reject) { // (A)
        if (true /* replace true with your own logic */) {
            resolve(value); // success
        } else {
            reject(reason); // failure
        }
    });
```

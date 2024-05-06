---
id: 1cd276d1-1af0-4472-aec6-bfd148cb5361
title: JavaScript Producing Promises
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

# Related

-   [JavaScript Promises](20200911154351-promises)

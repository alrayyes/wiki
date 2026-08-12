---
publish: true
title: JavaScript Producing Promises
created: 2020-11-11T09:52:30
modified: 2026-08-12T10:26:13.181Z
---

# JavaScript Producing Promises

## Advice

Use [[JavaScript Async Functions]] instead of this.

## Syntax

```js
const p = new Promise(
    function (resolve, reject) { // (A)
        if (true /* replace true with your own logic */) {
            resolve(value); // success
        } else {
            reject(reason); // failure
        }
    });
```

## Related

- [[JavaScript Promises]]

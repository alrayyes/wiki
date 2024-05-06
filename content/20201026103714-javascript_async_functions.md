---
id: 03f42b69-8321-443f-9d1d-fb7814999dd7
title: JavaScript Async Functions
---

# Introduction

Async Functions[^1] is a new feature implemented in
[ES2017](20201026104538-es2017) to handle
[promises](20200911154351-promises).

# Syntax

## Fulfilling a promise

``` javascript
async function asyncFunc() {
  return 123;
}

asyncFunc().then((x) => console.log(x));
// 123
```

## Rejecting a promise

``` javascript
async function asyncFunc() {
  throw new Error("Problem!");
}

asyncFunc().catch((err) => console.log(err));
// Error: Problem!
```

# Footnotes

[^1]: <https://github.com/tc39/ecmascript-asyncawait>

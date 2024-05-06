---
id: 189b65a7-906f-41fd-91cd-57c4cc5764d2
title: JavaScript Promises Finally
---

# Introduction

Like [Exceptions](20201111094033-javascript_exceptions_finally), since
[ES2018](20201030095105-es2018) JavaScript
[Promises](20200911154351-promises) also support `.finally()`.

# Syntax

``` javascript
promise
  .then((result) => {})
  .catch((error) => {})
  .finally(() => {});
```

## Shorthand

``` javascript
promise.finally(() => {});
```

is equal to

``` javascript
promise.then(
  (result) => {
    return result;
  },
  (error) => {
    throw error;
  }
);
```

---
publish: true
title: JavaScript Promises Finally
created: 2020-11-11T09:54:54
---

## Introduction

Like [[JavaScript Exceptions Finally]], since [[ES2018]] JavaScript [[JavaScript Promises]] also support ~.finally()~.

## Syntax

```js
promise
  .then((result) => {})
  .catch((error) => {})
  .finally(() => {});
```

### Shorthand

```js
promise.finally(() => {});
```

is equal to

```js
promise.then(
  (result) => {
    return result;
  },
  (error) => {
    throw error;
  }
);
```

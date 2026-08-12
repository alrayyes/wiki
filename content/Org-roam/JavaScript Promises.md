---
publish: true
title: JavaScript Promises
created: 2020-09-11T15:43:51
modified: 2026-08-12T10:26:13.181Z
---

# JavaScript Promises

## Introduction

A Promise[^footnote] is an asynchronous action that may complete at some point and produce a value. It is able to notify anyone who is interested when its value is available.

```js
let fifteen = Promise.resolve(15);
fifteen.then(value => console.log(`Got ${value}`))
```

## Parallel

- [[Executing Promises in Parallel (Promises.all)]]
- [[Promise.allSettled]]

## Errors

- [[Catching Promise Errors]]
- [[JavaScript Promises Finally]]

## Producing & Consuming

Use [[JavaScript Async Functions]] instead of this.

- [[Producing Promises]]
- [[JavaScript Consuming Promises]]

## Footnotes

[^footnote]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise

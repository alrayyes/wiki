---
publish: true
title: JavaScript Promises
created: 2020-09-11T15:43:51
modified: 2026-08-05T07:58:56.704Z
---

# JavaScript Promises

- [Introduction](#introduction)
- [Parallel](#parallel)
- [Errors](#errors)
- [Producing & Consuming](#producing--consuming)
- [Footnotes](#footnotes)

# Introduction

A Promise\[fn:footnote] is an asynchronous action that may complete at some point and produce a value. It is able to notify anyone who is interested when its value is available.

```js
let fifteen = Promise.resolve(15);
fifteen.then(value => console.log(`Got ${value}`))
```

# Parallel

- \[Executing Promises in Parallel (Promises.all)]\(Executing Promises in Parallel (Promises.all))
- [Promise.allSettled](Promise.allSettled)

# Errors

- \[Catching Promise Errors]\(Catching Promise Errors)
- \[JavaScript Promises Finally]\(JavaScript Promises Finally)

# Producing & Consuming

Use \[JavaScript Async Functions]\(JavaScript Async Functions) instead of this.

- \[Producing Promises]\(Producing Promises)
- \[JavaScript Consuming Promises]\(JavaScript Consuming Promises)

# Footnotes

\[fn:footnote]https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Promise

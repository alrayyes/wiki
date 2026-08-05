---
publish: true
title: JavaScript Promises Finally
created: 2020-11-11T09:54:54
modified: 2026-08-05T10:26:50.506Z
---

# JavaScript Promises Finally

# Introduction

Like \[JavaScript Exceptions Finally]\(JavaScript Exceptions Finally), since [ES2018](ES2018) JavaScript \[JavaScript Promises]\(JavaScript Promises) also support ~.finally()~.

# Syntax

promise
.then((result) => {})
.catch((error) => {})
.finally(() => {});

## Shorthand

promise.finally(() => {});

is equal to

promise.then(
(result) => {
return result;
},
(error) => {
throw error;
}
);

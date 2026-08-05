---
publish: true
title: JavaScript Custom Error Types
created: 2020-11-11T09:36:51
modified: 2026-08-05T07:58:56.688Z
---

# JavaScript Custom Error Types

- [Introduction](#introduction)
- [Syntax](#syntax)

# Introduction

Introduced in [ES6](ES6), [JavaScript](JavaScript) allows you to create your own custom error objects.

# Syntax

```js
class MyError extends Error {}

function tralala() {
    throw new MyError("blahblahblah")
}

try {
    tralala()
} catch (e) {
    if (e instanceof MyError) {
        console.log("Something went wrong with tralala");
    } else {
        throw e;
    }
}
```

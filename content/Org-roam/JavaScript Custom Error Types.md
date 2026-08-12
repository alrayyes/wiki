---
publish: true
title: JavaScript Custom Error Types
created: 2020-11-11T09:36:51
modified: 2026-08-12T09:44:58.331Z
---

# JavaScript Custom Error Types

## Introduction

Introduced in [[ES6]], [[JavaScript]] allows you to create your own custom error objects.

## Syntax

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

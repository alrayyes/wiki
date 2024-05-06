---
id: ce0d13cd-6680-4415-b375-c22de367cb21
title: JavaScript Custom Error Types
---

# Introduction

Introduced in [ES6](20201030093404-es6),
[JavaScript](20200613170905-javascript) allows you to create your own
custom error objects.

# Syntax

``` javascript
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

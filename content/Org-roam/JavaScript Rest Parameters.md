---
publish: true
title: JavaScript Rest Parameters
created: 2020-09-22T16:25:00
modified: 2026-08-12T10:26:13.182Z
---

# JavaScript Rest Parameters

## Introduction

Introduced in [[ES6]]

## Syntax

```js
function logAllArguments(...args) {
    for (const arg of args) {
        console.log(arg);
    }
}

logAllArguments(1, 2, 3)
```

```js
function logAllArguments(pattern, ...args) {
    console.log(pattern)
    for (const arg of args) {
        console.log(arg);
    }
}

logAllArguments("asdf", 1, 2, 3)
```

---
publish: true
title: JavaScript Exceptions Finally
created: 2020-11-11T09:40:33
modified: 2026-08-12T10:31:55.407Z
---

# JavaScript Exceptions Finally

## Description

Code in ~finally~ block is _always_ run after code in the ~try~ block:

## Syntax

```js
function baSays() {
    throw new Error("I pity the fool!")
}

try {
    baSays()
} catch (error) {
    console.log("This is the B.A. error: " + error)
} finally {
    console.log("This code is always run!")
}

function hannibalSays() {
    console.log("I love it when a plan comes together!")
}

try {
    hannibalSays()
} catch (error) {
    console.log("This is the Hannibal error: " + error)
} finally {
    console.log("This code is always run!")
}
```

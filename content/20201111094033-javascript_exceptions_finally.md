---
id: 06ffac8f-e131-4a17-8c88-7edbe3bd0cfd
title: JavaScript Exceptions Finally
---

# Description

Code in `finally` block is **always** run after code in the `try` block:

# Syntax

``` javascript
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

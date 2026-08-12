---
publish: true
title: JavaScript declaration notation
created: 2020-10-06T11:12:44
modified: 2026-08-12T09:44:58.331Z
---

# JavaScript declaration notation

There is a shorter way to declare functions:

```js
function square(x) {
    return x * x
}

console.log(square(5))
```

Function declarations are not part of the regular top-to-bottom flow on control. They are conceptually moved to the top of their scope and can be used by all the code in that scope.

```js
console.log("The future says:", future())

function future() {
    return "Where are my flying cars?"
}

```

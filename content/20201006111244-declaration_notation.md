---
id: 2b93c1c4-b0ed-4b03-846b-557ccc9d6080
title: JavaScript declaration notation
---

There is a shorter way to declare functions:

``` javascript
function square(x) {
    return x * x
}

console.log(square(5))
```

Function declarations are not part of the regular top-to-bottom flow on
control. They are conceptually moved to the top of their scope and can
be used by all the code in that scope.

``` javascript
console.log("The future says:", future())

function future() {
    return "Where are my flying cars?"
}

```

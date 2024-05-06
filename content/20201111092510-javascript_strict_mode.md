---
id: c5fef6b1-c659-42ef-8b51-7657df6743e8
title: JavaScript Strict Mode
---

# Description

[Strict
mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)
makes several changes to normal JavaScript semantics:

-   Eliminates some JavaScript silent errors by changing them to throw
    errors.
-   Fixes mistakes that make it difficult for JavaScript engines to
    perform optimizations: strict mode code can sometimes be made to run
    faster than identical code that's not strict mode.
-   Prohibits some syntax likely to be defined in future versions of
    ECMAScript.

``` javascript
function canYouSpotTheProblem() {
  "use strict";
  for (counter = 0; counter < 10; counter++) {
    console.log("Happy happy");
  }
}

canYouSpotTheProblem();
// → ReferenceError: counter is not defined
```

In strict mode the \`this\` binding holds the value \`undefined\` in
functions that are not called as methods:

``` javascript
"use strict";

function doSomething() {
    console.log(this)
}
```

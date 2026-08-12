---
publish: true
title: JavaScript Strict Mode
created: 2020-11-11T09:25:10
---

## Description

[Strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode) makes several changes to normal JavaScript semantics:

- Eliminates some JavaScript silent errors by changing them to throw errors.
- Fixes mistakes that make it difficult for JavaScript engines to perform optimizations: strict mode code can sometimes be made to run faster than identical code that's not strict mode.
- Prohibits some syntax likely to be defined in future versions of ECMAScript.

```js
function canYouSpotTheProblem() {
  "use strict";
  for (counter = 0; counter < 10; counter++) {
    console.log("Happy happy");
  }
}

canYouSpotTheProblem();
// → ReferenceError: counter is not defined
```

In strict mode the `this` binding holds the value `undefined` in functions that are not called as methods:

```js
"use strict";

function doSomething() {
    console.log(this)
}
```

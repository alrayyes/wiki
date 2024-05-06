---
id: dedc9e64-fe57-4c60-95b9-7df6201f4949
title: JavaScript Named parameters
---

# Introduction

Introduced with [ES6](20201030093404-es6)

# Syntax

``` javascript
function selectEntries({ start=0, end=-1, step=1 } = {}) {
    console.log(start)
    console.log(end)
    console.log(step)
}

selectEntries()
```

# See also

-   [Rest Operator (…) in Object
    Destructuring](20201103111357-rest_operator_in_object_destructuring)

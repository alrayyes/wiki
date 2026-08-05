---
publish: true
title: JavaScript Named parameters
created: 2020-09-22T16:21:27
modified: 2026-08-05T07:58:56.698Z
---

# JavaScript Named parameters

# Introduction

Introduced with [ES6](ES6)

# Syntax

```js
function selectEntries({ start=0, end=-1, step=1 } = {}) {
    console.log(start)
    console.log(end)
    console.log(step)
}

selectEntries()
```

# See also

- \[Rest Operator (...) in Object Destructuring]\(Rest Operator (...) in Object Destructuring)

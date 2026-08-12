---
publish: true
title: JavaScript Named parameters
created: 2020-09-22T16:21:27
modified: 2026-08-12T10:31:55.409Z
---

# JavaScript Named parameters

## Introduction

Introduced with [[ES6]]

## Syntax

```js
function selectEntries({ start=0, end=-1, step=1 } = {}) {
    console.log(start)
    console.log(end)
    console.log(step)
}

selectEntries()
```

## See also

- [[Rest Operator (...) in Object Destructuring]]

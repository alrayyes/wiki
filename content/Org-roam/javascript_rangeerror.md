---
publish: true
title: JavaScript RangeError
created: 2020-11-11T09:32:27
modified: 2026-08-05T07:58:56.691Z
---

# JavaScript RangeError

```js
// Call console with too many arguments
console.log.apply(console, new Array(1000000000)); // RangeError: Invalid array length
```

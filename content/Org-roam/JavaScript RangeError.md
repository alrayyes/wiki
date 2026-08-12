---
publish: true
title: JavaScript RangeError
created: 2020-11-11T09:32:27
---

```js
// Call console with too many arguments
console.log.apply(console, new Array(1000000000)); // RangeError: Invalid array length
```

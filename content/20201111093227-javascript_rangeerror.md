---
id: 67198605-05a4-4a1b-9083-d4e445b38344
title: JavaScript RangeError
---

``` javascript
// Call console with too many arguments
console.log.apply(console, new Array(1000000000)); // RangeError: Invalid array length
```

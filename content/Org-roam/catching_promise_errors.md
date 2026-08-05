---
publish: true
title: Catching Promise Errors
created: 2020-11-11T09:51:00
modified: 2026-08-05T10:26:50.495Z
---

# Catching Promise Errors

# Syntax

```js
new Promise((_, reject) => reject(new Error("Fail")))
  .then(value => console.log("Handler 1"))
  .catch(reason => {
    console.log("Caught failure " + reason);
    return "nothing";
  })
  .then(value => console.log("Handler 2", value));
```

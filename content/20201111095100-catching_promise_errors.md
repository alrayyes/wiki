---
id: af9d9cf2-a888-4e8e-8156-4c4a664450f1
title: Catching Promise Errors
---

# Syntax

``` javascript
new Promise((_, reject) => reject(new Error("Fail")))
  .then(value => console.log("Handler 1"))
  .catch(reason => {
    console.log("Caught failure " + reason);
    return "nothing";
  })
  .then(value => console.log("Handler 2", value));
```

---
id: 5efd4eb2-1e91-4fdf-8d83-18c0c1029d52
title: Promise.allSettled
---

# Description

Let every request finish no matter if others fail or not.

# Syntax

``` javascript
const promises = [Promise.resolve(1), Promise.reject(2)];
const [result1, result2] = await Promise.allSettled(promises);
```

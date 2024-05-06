---
id: 76fc0a0a-7d56-49c7-8c57-7686cca110fc
title: JavaScript RegExp /u flag
---

This flag matches astral characters such as emojis:

``` javascript
console.log(/^.$/u.test("🙂")); // true
```

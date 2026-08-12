---
publish: true
aliases:
  - JavaScript RegExp /u flag
title: JavaScript RegExp /u flag
created: 2020-11-10T09:51:39
modified: 2026-08-12T10:26:13.182Z
---

# JavaScript RegExp /u flag

This flag matches astral characters such as emojis:

```js
console.log(/^.$/u.test("🙂")); // true
```

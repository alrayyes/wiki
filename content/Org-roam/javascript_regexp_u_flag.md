---
publish: true
title: JavaScript RegExp /u flag
created: 2020-11-10T09:51:39
modified: 2026-08-05T10:26:50.506Z
---

# JavaScript RegExp /u flag

This flag matches astral characters such as emojis:

console.log(/^.\$/u.test("🙂")); // true

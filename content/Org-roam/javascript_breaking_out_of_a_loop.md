---
publish: true
title: JavaScript Breaking Out of a Loop
created: 2020-10-30T09:43:43
modified: 2026-08-05T07:58:56.688Z
---

# JavaScript Breaking Out of a Loop

# Syntax

```js
for (let current = 20; ; current = current + 1) {
  if (current % 7 == 0) {
    console.log(current);
    break;
  }
}
```

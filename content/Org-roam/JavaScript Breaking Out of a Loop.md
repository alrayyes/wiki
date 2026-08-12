---
publish: true
title: JavaScript Breaking Out of a Loop
created: 2020-10-30T09:43:43
modified: 2026-08-12T10:31:55.406Z
---

# JavaScript Breaking Out of a Loop

## Syntax

```js
for (let current = 20; ; current = current + 1) {
  if (current % 7 == 0) {
    console.log(current);
    break;
  }
}
```

---
id: 3b67edf8-727e-42c4-b46d-c096b2fb350b
title: JavaScript Breaking Out of a Loop
---

# Syntax

``` javascript
for (let current = 20; ; current = current + 1) {
  if (current % 7 == 0) {
    console.log(current);
    break;
  }
}
```

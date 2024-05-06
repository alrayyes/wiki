---
id: 32ffc92c-6a1d-4bf1-8f4c-b8d53ced6203
title: MatchAll Expression
---

# Description

Find all instances of a regular expression match, including the index.

# Syntax

``` javascript
const matches = "Here are some numbers: 5 12 88".matchAll(/\d+/g);
for (const match of matches) {
  console.log(match);
}
```

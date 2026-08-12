---
publish: true
title: MatchAll Expression
created: 2020-11-16T16:53:24
modified: 2026-08-12T09:44:58.341Z
---

# MatchAll Expression

## Description

Find all instances of a regular expression match, including the index.

## Syntax

```js
const matches = "Here are some numbers: 5 12 88".matchAll(/\d+/g);
for (const match of matches) {
  console.log(match);
}
```

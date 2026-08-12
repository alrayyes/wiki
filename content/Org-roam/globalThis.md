---
publish: true
title: globalThis
created: 2020-11-16T17:05:38
---

# globalThis

## Description

This eases yet another JavaScript pita. Replaces the different global object names:

- \~window~ (browser)
- \~global~ (node)
- \~self~ (web workers)

with ~globalThis~.

## Syntax

```js
if (typeof globalThis.alert === "function") {
  globalThis.alert("hi");
}
```

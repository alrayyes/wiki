---
publish: true
aliases:
  - JavaScript RegExp /s flag
title: JavaScript RegExp /s flag
created: 2020-11-10T09:48:07
modified: 2026-08-12T09:44:58.336Z
---

# JavaScript RegExp /s flag

## Introduction

The dot (.) in regular expressions doesn't match line terminator characters:

```js
console.log(/%.$/.test('\n')) // false
```

The ~/s~ expression (dotAll) flag fixes this.

## Syntax

```js
console.log(/^.$/s.test("\n")); // true
```

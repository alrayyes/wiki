---
publish: true
aliases:
  - JavaScript RegExp /s flag
title: JavaScript RegExp /s flag
created: 2020-11-10T09:48:07
---

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

---
id: 8bf1886a-0754-467f-a441-cb21bccfbd46
title: JavaScript RegExp /s flag
---

# Introduction

The dot (.) in regular expressions doesn't match line terminator
characters:

``` javascript
console.log(/%.$/.test('\n')) // false
```

The `/s` expression (dotAll) flag fixes this.

# Syntax

``` javascript
console.log(/^.$/s.test("\n")); // true
```

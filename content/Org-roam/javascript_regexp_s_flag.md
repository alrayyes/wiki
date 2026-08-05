---
publish: true
title: JavaScript RegExp /s flag
created: 2020-11-10T09:48:07
modified: 2026-08-05T07:58:56.692Z
---

# JavaScript RegExp /s flag

- [Introduction](#introduction)
- [Syntax](#syntax)

# Introduction

The dot (.) in regular expressions doesn't match line terminator characters:

console.log(/%.\$/.test('\n')) // false

The ~/s~ expression (dotAll) flag fixes this.

# Syntax

console.log(/^.\$/s.test("\n")); // true

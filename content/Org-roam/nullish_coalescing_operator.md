---
publish: true
title: Nullish coalescing operator (??)
created: 2020-11-16T16:22:37
modified: 2026-08-05T10:26:50.510Z
---

# Nullish coalescing operator (??)

# Description

Returns right-hand side operand when it's left-hand side operand is ~null~ or ~undefined~, and otherwise returns its left-hand side operand.

# Syntax

const foo = null ?? 'default string';
console.log(foo); // default string

const baz = 0 ?? 42;
console.log(baz); // 0

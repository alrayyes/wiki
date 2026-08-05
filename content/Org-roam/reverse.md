---
publish: true
title: reverse()
created: 2020-11-16T13:07:38
modified: 2026-08-05T07:58:56.706Z
---

# reverse()

# Description

Flips the order of the string contents.

# Syntax

use function Symfony\Component\String\u;

u('aeiou')->containsAny('a');                 // true
u('aeiou')->containsAny(\['ab', 'efg']);       // false
u('aeiou')->containsAny(\['eio', 'foo', 'z']); // true

---
publish: true
title: containsAny()
created: 2020-11-16T13:05:03
modified: 2026-08-12T10:31:55.392Z
---

# containsAny()

## Description

Checks if string contains at least one of all passed strings.

## Syntax

```php
use function Symfony\Component\String\u;

u('aeiou')->containsAny('a');                 // true
u('aeiou')->containsAny(['ab', 'efg']);       // false
u('aeiou')->containsAny(['eio', 'foo', 'z']); // true
```

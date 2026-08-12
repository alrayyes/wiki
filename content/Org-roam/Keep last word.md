---
publish: true
title: Keep last word
created: 2020-11-16T13:03:27
modified: 2026-08-12T10:31:55.416Z
---

# Keep last word

## Description

Keep last word when truncating.

## Syntax

```php
use function Symfony\Component\String\u;

u('Lorem Ipsum')->truncate(8, '…');        // 'Lorem I…'
u('Lorem Ipsum')->truncate(8, '…', false); // 'Lorem Ipsum'
```

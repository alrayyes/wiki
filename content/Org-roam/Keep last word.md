---
publish: true
title: Keep last word
created: 2020-11-16T13:03:27
---

## Description

Keep last word when truncating.

## Syntax

```php
use function Symfony\Component\String\u;

u('Lorem Ipsum')->truncate(8, '…');        // 'Lorem I…'
u('Lorem Ipsum')->truncate(8, '…', false); // 'Lorem Ipsum'
```

---
publish: true
title: PHP Named Arguments
created: 2020-11-12T11:19:10
modified: 2026-08-12T10:26:13.192Z
---

# PHP Named Arguments

## Description

Allowes named arguments[^rfc] to be used to access parameters in random order, as in [[JavaScript Named parameters]].

## Syntax

```php
function tralala(string $a, string $b, string $c)
{
    echo $a.' '.$b.' '.$c;
}

tralala(b: 'la', c: 'la', a: 'tra');
// tra la la
```

## Footnotes

[^rfc]: https://wiki.php.net/rfc/named_params

---
publish: true
title: PHP Static Return Type
created: 2020-11-10T10:23:32
modified: 2026-08-12T10:31:55.422Z
---

# PHP Static Return Type

## Description

Introduced in [[PHP 8.0]], static return types[^staticreturntype] guarantee that a method will return an instance of its object, and not that of a parent.

## Syntax

```php
class Foo
{
    public function tralala(): static
    {
        return $this;
    }
}
```

## Footnotes

[^staticreturntype]: https://wiki.php.net/rfc/static_return_type

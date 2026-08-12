---
publish: true
title: PHP Stringable Interface
created: 2020-11-10T10:34:09
modified: 2026-08-12T10:31:55.422Z
---

# PHP Stringable Interface

## Description

Since [[PHP 8.0]], the stringable interface[^stringable] is automatically added to classes that implement the ~\_\_toString()~ method

## Syntax

```php
class Foo
{
    public function __toString(): string
    {
        return 'foo';
    }
}

function bar(string|Stringable $stringable) { /* … */ }

bar(new Foo());
bar('abc');
```

## Footnotes

[^stringable]: https://wiki.php.net/rfc/stringable

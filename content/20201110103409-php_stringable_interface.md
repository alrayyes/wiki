---
id: f97470da-6833-4ecf-81e2-40dd04f6c2a1
title: PHP Stringable Interface
---

# Description

Since [PHP 8.0](20201109133834-php_8_0), the stringable interface[^1] is
automatically added to classes that implement the `__toString()` method

# Syntax

``` php
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

# Footnotes

[^1]: <https://wiki.php.net/rfc/stringable>

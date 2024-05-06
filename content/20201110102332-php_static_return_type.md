---
id: b2ffe647-59d6-43a1-9e10-d9a278580284
title: PHP Static Return Type
---

# Description

Introduced in [PHP 8.0](20201109133834-php_8_0), static return types[^1]
guarantee that a method will return an instance of its object, and not
that of a parent.

# Syntax

``` php
class Foo
{
    public function tralala(): static
    {
        return $this;
    }
}
```

# Footnotes

[^1]: <https://wiki.php.net/rfc/static_return_type>

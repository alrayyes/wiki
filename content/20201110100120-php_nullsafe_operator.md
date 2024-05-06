---
id: d07536b9-8d42-4b60-92a5-0348acb0a3db
title: PHP nullsafe operator
---

# Description

Introduced in [PHP 8.0](20201109133834-php_8_0), nullsafe operators[^1]
enable you to safely use methods that may return `null`.

# Syntax

``` php
class bar
{
    public function excellent(): string
    {
        return "excellent";
    }
}

class foo
{
    public function getBarOrNull(): ?bar
    {
        return rand(0, 1) === 1 ? new bar() : null;
    }
}

$foo = new foo();

echo $foo->getBarOrNull()?->excellent();
```

# Footnotes

[^1]: <https://wiki.php.net/rfc/nullsafe_operator>

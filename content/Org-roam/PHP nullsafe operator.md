---
publish: true
title: PHP nullsafe operator
created: 2020-11-10T10:01:20
---

## Description

Introduced in [[PHP 8.0]], nullsafe operators[^nullsafe] enable you to safely use methods that may return ~null~.

## Syntax

```php
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

## Footnotes

[^nullsafe]: https://wiki.php.net/rfc/nullsafe_operator

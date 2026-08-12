---
publish: true
title: PHP constructor property promotion
created: 2020-11-10T10:13:08
modified: 2026-08-12T09:32:15.626Z
---

# PHP constructor property promotion

## Description

Introduced in [[PHP 8.0]], constructor property promotions[^constructor] add new syntatctic sugar to create value & data transfer objects.

## Syntax

```php
class Money
{
    public Currency $currency;

    public int $amount;

    public function __construct(
        Currency $currency,
        int $amount,
    ) {
        $this->currency = $currency;
        $this->amount = $amount;
    }
}
```

can be replaced with

```php
class Money
{
    public function __construct(
        public Currency $currency,
        public int $amount,
    ) {}
}
```

## Footnotes

[^constructor]: https://wiki.php.net/rfc/constructor_promotion

---
id: 19579c31-1dcc-4d11-b2f8-5f9180fa66d3
title: PHP constructor property promotion
---

# Description

Introduced in [PHP 8.0](20201109133834-php_8_0), constructor property
promotions[^1] add new syntatctic sugar to create value & data transfer
objects.

# Syntax

``` php
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

``` php
class Money
{
    public function __construct(
        public Currency $currency,
        public int $amount,
    ) {}
}
```

# Footnotes

[^1]: <https://wiki.php.net/rfc/constructor_promotion>

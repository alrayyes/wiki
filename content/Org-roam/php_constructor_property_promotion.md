---
publish: true
title: PHP constructor property promotion
created: 2020-11-10T10:13:08
modified: 2026-08-05T07:58:56.701Z
---

# PHP constructor property promotion

# Description

Introduced in \[PHP 8.0]\(PHP 8.0), constructor property promotions\[fn:constructor] add new syntatctic sugar to create value & data transfer objects.

# Syntax

class Money
{
public Currency \$currency;

```
public int $amount;

public function __construct(
    Currency $currency,
    int $amount,
) {
    $this->currency = $currency;
    $this->amount = $amount;
}
```

}

can be replaced with

class Money
{
public function \_\_construct(
public Currency $currency,
        public int $amount,
) {}
}

# Footnotes

\[fn:constructor]https://wiki.php.net/rfc/constructor\_promotion

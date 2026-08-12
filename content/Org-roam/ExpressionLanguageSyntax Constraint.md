---
publish: true
title: ExpressionLanguageSyntax Constraint
created: 2020-11-16T13:55:23
modified: 2026-08-12T10:26:13.168Z
---

# ExpressionLanguageSyntax Constraint

## Description

Checks that passed [[ExpressionLanguage Constraint]] is valid.

## Syntax

```php
namespace App\Entity;

use Symfony\Component\Validator\Constraints as Assert;

class Order
{
    /**
     * @Assert\ExpressionLanguageSyntax()
     */
    protected $promotion;

    /**
     * @Assert\ExpressionLanguageSyntax(
     *     names = ['user', 'shipping_centers'],
     *     validateNames = true
     * )
     */
    protected $shippingOptions;
}
```

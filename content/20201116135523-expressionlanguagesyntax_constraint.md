---
id: 3a90ffd1-7d51-4ade-ad6e-8924c15d956d
title: ExpressionLanguageSyntax Constraint
---

# Description

Checks that passed [expression
language](20201109150640-expressionlanguage_constraint) is valid.

# Syntax

``` php
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

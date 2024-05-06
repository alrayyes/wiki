---
id: 5cc7016f-2142-47c3-b256-d295a58339a7
title: Symfony DivisibleBy Constraint
---

# Introduction

Introduced in [Symfony 4.2](20201111101706-symfony_4_2), `DivisibleBy`
enforces specific increments on a number.

# Syntax

``` php
// src/Entity/Item.php
namespace App\Entity;
use Symfony\Component\Validator\Constraints as Assert;

class Item
{
    /**
     * @Assert\DivisibleBy(0.25)
     */
    protected $weight;

    /**
     * @Assert\DivisibleBy(
     *     value = 5,
     *     message = "This item requires to be stocked in multiples of 5 units."
     * )
     */
    protected $quantity;
}
```

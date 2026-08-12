---
publish: true
title: Symfony DivisibleBy Constraint
created: 2020-11-11T10:30:48
modified: 2026-08-12T09:44:58.356Z
---

# Symfony DivisibleBy Constraint

## Introduction

Introduced in [[Symfony 4.2]], ~DivisibleBy~ enforces specific increments on a number.

## Syntax

```php
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

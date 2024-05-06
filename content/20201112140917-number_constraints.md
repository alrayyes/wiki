---
id: adc652c4-6f67-46e9-a975-8e72b852234c
title: Number Constraints
---

# Syntax

``` php
use Symfony\Component\Validator\Constraints as Assert;

class Person
{
    /** @Assert\PositiveOrZero */
    protected $siblings;

    // ...
}

class Employee
{
    /** @Assert\Positive */
    protected $income;

    // ...
}

class UnderGroundGarage
{
    /** @Assert\NegativeOrZero */
    protected $level;

    // ...
}

class TransferItem
{
    /** @Assert\Negative */
    protected $withdraw;

    // ...
}
```

---
publish: true
title: Number Constraints
created: 2020-11-12T14:09:17
---

# Number Constraints

## Syntax

```php
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

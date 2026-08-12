---
publish: true
title: Expression Constraint
created: 2020-11-09T15:06:40
modified: 2026-08-12T10:26:13.167Z
---

# Expression Constraint

## Syntax

```php
use Symfony\Component\Validator\Constraints as Assert;

class Event
{
    /** @Assert\DateTime() */
    private $startDate;

    /**
     * @Assert\DateTime()
     * @Assert\Expression("value > this.startDate")
     */
    private $endDate;

    // ...
}
```

In [[Symfony 4.0]] a new ~propertyPath~ option was added:

```php
use Symfony\Component\Validator\Constraints as Assert;

class Event
{
    /** @Assert\DateTime() */
    private $startDate;

    /**
     * @Assert\DateTime()
     * @Assert\GreaterThan(propertyPath="startDate")
     */
    private $endDate;

    // ...
}
```

---
id: 4331b4ee-c987-4e04-8a46-3b8d30e13581
title: Expression Constraint
---

# Syntax

``` php
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

In [Symfony 4.0](20201109140137-symfony_4_0) a new `propertyPath` option
was added:

``` php
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

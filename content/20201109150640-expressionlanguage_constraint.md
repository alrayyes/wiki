---
id: cafa5c65-3517-4e04-b724-a7e3b467142d
title: ExpressionLanguage Constraint
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

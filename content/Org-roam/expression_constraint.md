---
publish: true
title: Expression Constraint
created: 2020-11-09T15:06:40
modified: 2026-08-05T10:26:50.500Z
---

# Expression Constraint

# Syntax

use Symfony\Component\Validator\Constraints as Assert;

class Event
{
/\*\* @Assert\DateTime() \*/
private \$startDate;

```
/**
 * @Assert\DateTime()
 * @Assert\Expression("value > this.startDate")
 */
private $endDate;

// ...
```

}

In \[Symfony 4.0]\(Symfony 4.0) a new ~propertyPath~ option was added:

use Symfony\Component\Validator\Constraints as Assert;

class Event
{
/\*\* @Assert\DateTime() \*/
private \$startDate;

```
/**
 * @Assert\DateTime()
 * @Assert\GreaterThan(propertyPath="startDate")
 */
private $endDate;

// ...
```

}

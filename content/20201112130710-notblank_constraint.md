---
id: ba104198-9038-4219-994e-503ee655d9f3
title: NotBlank Constraint
---

# Syntax

``` php
namespace App\Entity;

use Symfony\Component\Validator\Constraints as Assert;

class SomeEntity
{
    /**
     * @Assert\NotBlank()
     */
    protected $someProperty;
}
```

## allowNull

[NotBlank allowNull](20201112130816-notblank_allownull)

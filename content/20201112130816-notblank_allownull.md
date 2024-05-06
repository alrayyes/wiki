---
id: 47dd501e-a567-481a-8d85-5eb1cd0bad15
title: NotBlank allowNull
---

# Description

The default option is `false`. If set to true then `null` values will be
considered valid.

# Syntax

``` php
namespace App\Entity;

use Symfony\Component\Validator\Constraints as Assert;

class SomeEntity
{
    /**
     * @Assert\NotBlank(allowNull = true)
     */
    protected $someProperty;
}

```

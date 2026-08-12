---
publish: true
title: NotBlank allowNull
created: 2020-11-12T13:08:16
modified: 2026-08-12T10:26:13.189Z
---

# NotBlank allowNull

## Description

The default option is ~false~. If set to true then ~null~ values will be considered valid.

## Syntax

```php
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

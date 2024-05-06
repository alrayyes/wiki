---
id: 4e20e5e5-06b6-4280-9cd0-7b08585a762b
title: Symfony JSON Constraint
---

# Syntax

``` php
// src/Entity/Book.php
namespace App\Entity;

use Symfony\Component\Validator\Constraints as Assert;

class Book
{
    /**
     * @Assert\Json(message = "This is not valid JSON")
     */
     protected $chapters;
}
```

---
publish: true
title: Symfony JSON Constraint
created: 2020-11-12T12:56:37
---

# Symfony JSON Constraint

## Syntax

```php
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

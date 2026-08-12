---
publish: true
title: ULID Constraint
created: 2020-11-17T10:43:32
modified: 2026-08-12T09:32:15.643Z
---

# ULID Constraint

## Syntax

```php
// src/Entity/Product.php
namespace App\Entity;

use Doctrine\ORM\Mapping as ORM;
use Symfony\Component\Validator\Constraints as Assert;

/**
 * @ORM\Entity(repositoryClass="App\Repository\ProductRepository")
 */
class Product
{
    /**
     * @ORM\Column(type="ulid")
     * @Assert\Ulid
     */
    private $someProperty;

    // ...
}
```

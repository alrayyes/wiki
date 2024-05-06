---
id: e8cb1177-6034-441f-a23e-bcdbf5a31fa6
title: Type Constraint Can Be An Array of Types
---

# Syntax

``` php
// src/Entity/Author.php
namespace App\Entity;

use Symfony\Component\Validator\Constraints as Assert;

class Author
{
    // ...

    /**
     * @Assert\Type(type={"alpha", "digit"})
     */
    protected $accessCode;
}
```

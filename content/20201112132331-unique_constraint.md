---
id: ebceb7b8-5242-482b-b258-2cf9c25d1788
title: Unique Constraint
---

# Syntax

``` php
// src/Entity/Person.php
namespace App\Entity;

use Symfony\Component\Validator\Constraints as Assert;

class Person
{
    /**
     * @Assert\Unique(message="The {{ value }} email is repeated.")
     */
    protected $contactEmails;
}
```

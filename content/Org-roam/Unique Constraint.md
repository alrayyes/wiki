---
publish: true
title: Unique Constraint
created: 2020-11-12T13:23:31
modified: 2026-08-12T10:31:55.444Z
---

# Unique Constraint

## Syntax

```php
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

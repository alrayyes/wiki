---
publish: true
title: NotBlank Constraint
created: 2020-11-12T13:07:10
modified: 2026-08-12T10:26:13.189Z
---

# NotBlank Constraint

## Syntax

```php
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

### allowNull

[[NotBlank allowNull]]

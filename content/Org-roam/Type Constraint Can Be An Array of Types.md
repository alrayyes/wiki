---
publish: true
title: Type Constraint Can Be An Array of Types
created: 2020-11-13T17:28:16
modified: 2026-08-12T10:26:13.210Z
---

# Type Constraint Can Be An Array of Types

## Syntax

```php
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

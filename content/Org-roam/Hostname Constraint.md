---
publish: true
title: Hostname Constraint
created: 2020-11-16T13:24:11
---

# Hostname Constraint

## Description

Validates hostname

## Syntax

```php
// src/Entity/ServerSettings.php
namespace App\Entity;

use Symfony\Component\Validator\Constraints as Assert;

class ServerSettings
{
    /**
     * @Assert\Hostname(message="The server name must be a valid hostname.")
     */
    protected $name;
}
```

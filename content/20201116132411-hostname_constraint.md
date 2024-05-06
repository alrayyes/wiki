---
id: de7c8974-5636-4e6d-baf7-afc90985c535
title: Hostname Constraint
---

# Description

Validates hostname

# Syntax

``` php
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

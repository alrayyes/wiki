---
id: 1b282a21-2736-404a-a788-5a362fcba479
title: Compromised Password Constraint
---

# Description

Internally, the constraint makes an HTTP request to the API provided by
the haveibeenpwned.com website. In the request, the validator doesn't
send the raw password but only the few first characters of the result of
encoding it using SHA-1.

# Syntax

``` php
// src/Entity/User.php
namespace App\Entity;

use Symfony\Component\Validator\Constraints as Assert;

class User
{
    // ...

    /**
     * @Assert\NotCompromisedPassword
     */
    protected $rawPassword;
}
```

---
publish: true
title: Compromised Password Constraint
created: 2020-11-12T13:47:52
modified: 2026-08-12T09:32:15.598Z
---

# Compromised Password Constraint

## Description

Internally, the constraint makes an HTTP request to the API provided by the haveibeenpwned.com website. In the request, the validator doesn't send the raw password but only the few first characters of the result of encoding it using SHA-1.

## Syntax

```php
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

---
publish: true
title: Groups support for Valid constraint
created: 2020-11-09T14:57:24
modified: 2026-08-12T09:44:58.326Z
---

# Groups support for Valid constraint

## Introduction

As per [[Symfony 4.0]] validation groups are supported for the ~Valid~ constraint.

## Syntax

```php
// src/AppBundle/Entity/Address.php
// ...
class Address
{
    /** @Assert\NotBlank(groups={"basic"}) */
    protected $street;

    /** @Assert\Length(max = 5) */
    protected $zipCode;
}

// src/AppBundle/Entity/Author.php
// ...
class Author
{
    /** @Assert\NotBlank */
    protected $firstName;

    /** @Assert\NotBlank */
    protected $lastName;

    /** @Assert\Valid(groups={"basic"}) */
    protected $address;
}
```

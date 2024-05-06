---
id: 5da0c739-af47-49dd-84ea-bb2e48e4a9d8
title: Groups support for Valid constraint
---

# Introduction

As per [Symfony 4.0](20201109140137-symfony_4_0) validation groups are
supported for the `Valid` constraint.

# Syntax

``` php
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

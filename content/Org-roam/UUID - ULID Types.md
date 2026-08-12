---
publish: true
aliases:
  - UUID / ULID Types
title: UUID / ULID Types
created: 2020-11-17T10:14:52
modified: 2026-08-12T09:32:15.644Z
---

# UUID / ULID Types

## Description

Symfony has [[Doctrine]] types and generators for [[Symfony UUID Component]]

## Syntax

```php
// src/Entity/Product.php
namespace App\Entity;

use Doctrine\ORM\Mapping as ORM;

/**
 * @ORM\Entity(repositoryClass="App\Repository\ProductRepository")
 */
class Product
{
    /**
     * @ORM\Column(type="uuid")
     */
    private $someProperty;

    /**
     * @ORM\Column(type="ulid")
     */
    private $anotherProperty;

    // ...
}
```

```php
// there are generators for UUID V1 and V6 too
use Symfony\Bridge\Doctrine\IdGenerator\UuidV4Generator;

/**
 * @ORM\Entity(repositoryClass="App\Repository\ProductRepository")
 */
class Product
{
    /**
     * @ORM\Id
     * @ORM\Column(type="uuid", unique=true)
     * @ORM\GeneratedValue(strategy="CUSTOM")
     * @ORM\CustomIdGenerator(class=UuidV4Generator::class)
     */
    private $id;

    // ...
}


use Symfony\Bridge\Doctrine\IdGenerator\UlidGenerator;

/**
 * @ORM\Entity(repositoryClass="App\Repository\ProductRepository")
 */
class Product
{
    /**
     * @ORM\Id
     * @ORM\Column(type="ulid", unique=true)
     * @ORM\GeneratedValue(strategy="CUSTOM")
     * @ORM\CustomIdGenerator(class=UlidGenerator::class)
     */
    private $id;

    // ...
}
```

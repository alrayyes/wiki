---
publish: true
title: UUID / ULID Types
created: 2020-11-17T10:14:52
modified: 2026-08-05T07:58:56.721Z
---

# UUID / ULID Types

# Description

Symfony has [Doctrine](Doctrine) types and generators for \[Symfony UUID Component]\(Symfony UUID Component)

# Syntax

// src/Entity/Product.php
namespace App\Entity;

use Doctrine\ORM\Mapping as ORM;

/\*\*

- @ORM\Entity(repositoryClass="App\Repository\ProductRepository")
  _/
  class Product
  {
  /_\*

  - @ORM\Column(type="uuid")
    \*/
    private \$someProperty;

  /\*\*

  - @ORM\Column(type="ulid")
    \*/
    private \$anotherProperty;

  // ...
  }

// there are generators for UUID V1 and V6 too
use Symfony\Bridge\Doctrine\IdGenerator\UuidV4Generator;

/\*\*

- @ORM\Entity(repositoryClass="App\Repository\ProductRepository")
  _/
  class Product
  {
  /_\*

  - @ORM\Id
  - @ORM\Column(type="uuid", unique=true)
  - @ORM\GeneratedValue(strategy="CUSTOM")
  - @ORM\CustomIdGenerator(class=UuidV4Generator::class)
    \*/
    private \$id;

  // ...
  }

use Symfony\Bridge\Doctrine\IdGenerator\UlidGenerator;

/\*\*

- @ORM\Entity(repositoryClass="App\Repository\ProductRepository")
  _/
  class Product
  {
  /_\*

  - @ORM\Id
  - @ORM\Column(type="ulid", unique=true)
  - @ORM\GeneratedValue(strategy="CUSTOM")
  - @ORM\CustomIdGenerator(class=UlidGenerator::class)
    \*/
    private \$id;

  // ...
  }

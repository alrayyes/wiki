---
publish: true
title: UUID Normalizer
created: 2020-11-17T10:39:57
modified: 2026-08-05T07:58:56.721Z
---

# UUID Normalizer

# Description

\[Symfony UUID Component]\(Symfony UUID Component) are automatically serialized/deserialized as expected.

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
    private \$id;

  // ...
  }

$product = new Product();
$jsonContent = $serializer->serialize($product, 'json');
// \$jsonContent contains {"id":"9b7541de-6f87-11ea-ab3c-9da9a81562fc","...":"..."}

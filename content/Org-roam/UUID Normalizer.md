---
publish: true
title: UUID Normalizer
created: 2020-11-17T10:39:57
modified: 2026-08-12T09:44:58.366Z
---

# UUID Normalizer

## Description

[[Symfony UUID Component]] are automatically serialized/deserialized as expected.

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
    private $id;

    // ...
}
```

```php
$product = new Product();
$jsonContent = $serializer->serialize($product, 'json');
// $jsonContent contains {"id":"9b7541de-6f87-11ea-ab3c-9da9a81562fc","...":"..."}
```

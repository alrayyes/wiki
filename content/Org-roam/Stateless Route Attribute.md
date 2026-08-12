---
publish: true
title: Stateless Route Attribute
created: 2020-11-16T13:10:57
modified: 2026-08-12T09:44:58.353Z
---

# Stateless Route Attribute

## Description

When set to ~true~ declare that [[Sessions]] can't be used during handling of request. Generates Exception if route tries to use the [[Sessions]].

## Syntax

```php
// src/Controller/MainController.php
namespace App\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\Routing\Annotation\Route;

class MainController extends AbstractController
{
    /**
     * @Route("/", name="homepage", stateless=true)
     */
    public function homepage()
    {
        // ...
    }
}
```

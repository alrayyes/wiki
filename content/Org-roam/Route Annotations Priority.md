---
publish: true
title: Route Annotations Priority
created: 2020-11-16T12:38:57
modified: 2026-08-12T09:32:15.629Z
---

# Route Annotations Priority

## Description

Defines rouuting priority, defaults to ~0~

## Syntax

```php
use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\Routing\Annotation\Route;

class MyController extends AbstractController
{
    /**
     * @Route("/{some_parameter}", name="route1")
     */
    public function someMethod(): Response
    {
        // ...
    }

    /**
     * @Route("/foo", priority=10, name="route2")
     */
    public function anotherMethod(): Response
    {
        // ...
    }
}
```

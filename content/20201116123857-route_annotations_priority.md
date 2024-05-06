---
id: 19c60d30-34c0-49e2-bac9-764c0252ed96
title: Route Annotations Priority
---

# Description

Defines rouuting priority, defaults to `0`

# Syntax

``` php
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

---
publish: true
title: Route
created: 2020-11-17T10:50:45
modified: 2026-08-12T10:31:55.426Z
---

# Route

## Description

[[PHP Attributes]] can be used to define routing.

## Syntax

```php
// BEFORE: annotations defined with Doctrine Annotations library
use Symfony\Component\Routing\Annotation\Route;

class SomeController
{
    /**
     * @Route("/path", name="action")
     */
    public function someAction()
    {
        // ...
    }
}
```

```php
// AFTER: annotations defined with PHP 8 attributes
use Symfony\Component\Routing\Annotation\Route;

class SomeController
{
    #[Route('/path', name: 'action')]
    public function someAction()
    {
        // ...
    }
}
```

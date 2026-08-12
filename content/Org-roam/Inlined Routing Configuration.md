---
publish: true
title: Inlined Routing Configuration
created: 2020-11-10T15:42:29
---

## Introduction

Added in [[Symfony 4.1]], inlined routing configuration allows us to define requirements and default values for route placeholders.

## Syntax

```php
use Symfony\Component\Routing\Annotation\Route;

class BlogController extends Controller
{
    /**
     * @Route("/blog/{page}", name="blog_list", requirements={"page"="\d+"}, defaults={"page"="1"})
     */
    public function list($page)
    {
        // ...
    }
}
```

is now

```php
/**
 * @Route("/blog/{page<\d+>?1}", name="blog_list")
 */
public function list($page)
{
    // ...
}
```

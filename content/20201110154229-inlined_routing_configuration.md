---
id: e85e1d41-4327-4a38-b4f9-205e7ccec209
title: Inlined Routing Configuration
---

# Introduction

Added in [Symfony 4.1](20201110152518-symfony_4_1), inlined routing
configuration allows us to define requirements and default values for
route placeholders.

# Syntax

``` php
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

``` php
/**
 * @Route("/blog/{page<\d+>?1}", name="blog_list")
 */
public function list($page)
{
    // ...
}
```

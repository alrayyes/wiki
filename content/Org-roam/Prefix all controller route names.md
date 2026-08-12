---
publish: true
title: Prefix all controller route names
created: 2020-11-09T14:23:51
modified: 2026-08-12T09:32:15.627Z
---

# Prefix all controller route names

## Introduction

From [[Symfony 4.0]] the class of a controller can define the ~@Route~ annotation to set a common prefix for the URLs used by the action methods:

## Syntax

```php
use Sensio\Bundle\FrameworkExtraBundle\Configuration\Route;

/**
 * @Route("/blog")
 */
class BlogController extends Controller
{
    /**
     * @Route("/", defaults={"page": "1"}, name="blog_index")
     * @Route("/page/{page}", name="blog_index_paginated")
     */
    public function indexAction($page, $_format) { ... }

    /**
     * @Route("/posts/{slug}", name="blog_post")
     */
    public function showAction(Post $post) { ... }
}
```

Add a ~name~ property to the ~@Route~ annotation of the controller class and that will be considered the prefix of all route names. The following is equivalent to the previous example:

```php
use Sensio\Bundle\FrameworkExtraBundle\Configuration\Route;

/**
 * @Route("/blog", name="blog_")
 */
class BlogController extends Controller
{
    /**
     * @Route("/", defaults={"page": "1"}, name="index")
     * @Route("/page/{page}", name="index_paginated")
     */
    public function indexAction($page, $_format) { ... }

    /**
     * @Route("/posts/{slug}", name="post")
     */
    public function showAction(Post $post) { ... }
}
```

## name\_prefix option

In [[Symfony 4.1]] a new [[name_prefix]] option was added.

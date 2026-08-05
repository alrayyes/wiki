---
publish: true
title: Prefix all controller route names
created: 2020-11-09T14:23:51
modified: 2026-08-05T10:26:50.513Z
---

# Prefix all controller route names

- [Introduction](#introduction)
- [Syntax](#syntax)
- [name\_prefix option](#name_prefix-option)

# Introduction

From \[Symfony 4.0]\(Symfony 4.0) the class of a controller can define the ~@Route~ annotation to set a common prefix for the URLs used by the action methods:

# Syntax

use Sensio\Bundle\FrameworkExtraBundle\Configuration\Route;

/\*\*

- @Route("/blog")
  _/
  class BlogController extends Controller
  {
  /_\*

  - @Route("/", defaults={"page": "1"}, name="blog\_index")
  - @Route("/page/{page}", name="blog\_index\_paginated")
    \*/
    public function indexAction($page, $\_format) { ... }

  /\*\*

  - @Route("/posts/{slug}", name="blog\_post")
    \*/
    public function showAction(Post \$post) { ... }
    }

Add a ~name~ property to the ~@Route~ annotation of the controller class and that will be considered the prefix of all route names. The following is equivalent to the previous example:

use Sensio\Bundle\FrameworkExtraBundle\Configuration\Route;

/\*\*

- @Route("/blog", name="blog\_")
  _/
  class BlogController extends Controller
  {
  /_\*

  - @Route("/", defaults={"page": "1"}, name="index")
  - @Route("/page/{page}", name="index\_paginated")
    \*/
    public function indexAction($page, $\_format) { ... }

  /\*\*

  - @Route("/posts/{slug}", name="post")
    \*/
    public function showAction(Post \$post) { ... }
    }

# name\_prefix option

In \[Symfony 4.1]\(Symfony 4.1) a new [name\_prefix](name_prefix) option was added.

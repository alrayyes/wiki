---
publish: true
title: Inlined Routing Configuration
created: 2020-11-10T15:42:29
modified: 2026-08-05T07:58:56.686Z
---

# Inlined Routing Configuration

# Introduction

Added in \[Symfony 4.1]\(Symfony 4.1), inlined routing configuration allows us to define requirements and default values for route placeholders.

# Syntax

use Symfony\Component\Routing\Annotation\Route;

class BlogController extends Controller
{
/\*\*
\* @Route("/blog/{page}", name="blog\_list", requirements={"page"="\d+"}, defaults={"page"="1"})
\*/
public function list(\$page)
{
// ...
}
}

is now

/\*\*

- @Route("/blog/{page<\d+>?1}", name="blog\_list")
  \*/
  public function list(\$page)
  {
  // ...
  }

---
publish: true
title: Route
created: 2020-11-17T10:50:45
modified: 2026-08-05T07:58:56.707Z
---

# Route

# Description

\[PHP Attributes]\(PHP Attributes) can be used to define routing.

# Syntax

// BEFORE: annotations defined with Doctrine Annotations library
use Symfony\Component\Routing\Annotation\Route;

class SomeController
{
/\*\*
\* @Route("/path", name="action")
\*/
public function someAction()
{
// ...
}
}

// AFTER: annotations defined with PHP 8 attributes
use Symfony\Component\Routing\Annotation\Route;

class SomeController
{
\#\[Route('/path', name: 'action')]
public function someAction()
{
// ...
}
}

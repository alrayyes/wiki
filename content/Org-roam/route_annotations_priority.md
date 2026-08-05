---
publish: true
title: Route Annotations Priority
created: 2020-11-16T12:38:57
modified: 2026-08-05T07:58:56.707Z
---

# Route Annotations Priority

# Description

Defines rouuting priority, defaults to ~0~

# Syntax

use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\Routing\Annotation\Route;

class MyController extends AbstractController
{
/\*\*
\* @Route("/{some\_parameter}", name="route1")
\*/
public function someMethod(): Response
{
// ...
}

```
/**
 * @Route("/foo", priority=10, name="route2")
 */
public function anotherMethod(): Response
{
    // ...
}
```

}

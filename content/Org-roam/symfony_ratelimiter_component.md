---
publish: true
title: Symfony RateLimiter Component
created: 2020-11-17T11:34:04
modified: 2026-08-05T07:58:56.714Z
---

# Symfony RateLimiter Component

# Description

Introduced in \[Symfony 5.2]\(Symfony 5.2). See documentation\[fn:documentation]

# Syntax

# config/packages/rate\_limiter.yaml

framework:
rate\_limiter:
anonymous\_api:
strategy: fixed\_window
limit: 60
interval: '60 minutes'

// src/Controller/ApiController.php
namespace App\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\HttpKernel\Exception\TooManyRequestsHttpException;
use Symfony\Component\RateLimiter\Limiter;

class ApiController extends AbstractController
{
// the variable name must be: "rate limiter name" + "limiter" suffix
public function index(Limiter $anonymousApiLimiter)
    {
        // create a limiter based on the client's IP address
        // (you can also use a username/email, an API key, etc.)
        $limiter = $anonymousApiLimiter->create($request->getClientIp());

```
    // try to consume a resource; if it's accepted, serve the request
    // otherwise, return a 429 (Too Many Requests) error
    if (false === $limiter->consume()->isAccepted()) {
        throw new TooManyRequestsHttpException();
    }

    // ...
}

// ...
```

}

# Used by

- \[Login Throttling]\(Login Throttling)

# Footnotes

\[fn:documentation]https://github.com/symfony/symfony-docs/blob/5.x/rate\_limiter.rst

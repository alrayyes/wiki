---
publish: true
title: Symfony RateLimiter Component
created: 2020-11-17T11:34:04
---

## Description

Introduced in [[Symfony 5.2]]. See documentation[^documentation]

## Syntax

```yaml
# config/packages/rate_limiter.yaml
framework:
    rate_limiter:
        anonymous_api:
            strategy: fixed_window
            limit: 60
            interval: '60 minutes'
```

```php
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

        // try to consume a resource; if it's accepted, serve the request
        // otherwise, return a 429 (Too Many Requests) error
        if (false === $limiter->consume()->isAccepted()) {
            throw new TooManyRequestsHttpException();
        }

        // ...
    }

    // ...
}
```

## Used by

- [[Login Throttling]]

## Footnotes

[^documentation]: https://github.com/symfony/symfony-docs/blob/5.x/rate_limiter.rst

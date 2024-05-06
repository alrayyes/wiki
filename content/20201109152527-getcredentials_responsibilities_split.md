---
id: 9e629f0c-33c0-45bb-a978-623b13b2ffa5
title: getCredentials() responsibilities split
---

Since [Symfony 4.0](20201109140137-symfony_4_0) `getCredentials()`
responsibilities has been split into 2 methods:

``` php
// BEFORE
use Symfony\Component\Security\Guard\AbstractGuardAuthenticator;

class TokenAuthenticator extends AbstractGuardAuthenticator
{
    public function getCredentials(Request $request)
    {
        if (!$token = $request->headers->get('X-AUTH-TOKEN')) {
            return null;
        }

        return ['token' => $token];
    }
}

// AFTER
class TokenAuthenticator extends AbstractGuardAuthenticator
{
    public function supports(Request $request)
    {
        return $request->headers->has('X-AUTH-TOKEN');
    }

    public function getCredentials(Request $request)
    {
        return ['token' => $request->headers->get('X-AUTH-TOKEN')];
    }
}

```

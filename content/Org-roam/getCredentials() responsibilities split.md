---
publish: true
title: getCredentials() responsibilities split
created: 2020-11-09T15:25:27
modified: 2026-08-12T09:44:58.324Z
---

# getCredentials() responsibilities split

Since [[Symfony 4.0]] ~getCredentials()~ responsibilities has been split into 2 methods:

```php
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

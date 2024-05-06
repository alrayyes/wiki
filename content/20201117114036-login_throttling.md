---
id: ae0c6979-3374-4e8d-8cd8-cfe534e36261
title: Login Throttling
---

# Description

Uses the [Symfony RateLimiter
Component](20201117113404-symfony_ratelimiter_component) to throttle
brute force attacks.

# Syntax

``` yaml
# config/packages/security.yaml
security:
    firewalls:
        default:
            # by default, the feature allows 5 login attempts per minute
            login_throttling: ~

            # configuring the maximum login attempts (per minute)
            login_throttling:
                max_attempts: 1

            # you can even use a custom rate limiter via its service ID
            login_throttling:
                limiter: app.my_login_rate_limiter
```

# Caveats

Need to use Authenticator-based Security[^1]

# Footnotes

[^1]: <https://symfony.com/doc/current/security/experimental_authenticators.html>

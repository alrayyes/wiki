---
publish: true
title: Login Throttling
created: 2020-11-17T11:40:36
modified: 2026-08-05T10:26:50.509Z
---

# Login Throttling

# Description

Uses the \[Symfony RateLimiter Component]\(Symfony RateLimiter Component) to throttle brute force attacks.

# Syntax

# config/packages/security.yaml

security:
firewalls:
default:
\# by default, the feature allows 5 login attempts per minute
login\_throttling: ~

```
        # configuring the maximum login attempts (per minute)
        login_throttling:
            max_attempts: 1

        # you can even use a custom rate limiter via its service ID
        login_throttling:
            limiter: app.my_login_rate_limiter
```

# Caveats

Need to use Authenticator-based Security\[fn:authenticator]

# Footnotes

\[fn:authenticator]https://symfony.com/doc/current/security/experimental\_authenticators.html

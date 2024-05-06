---
id: bf86be19-256d-408e-b26e-dcd30d4f1e39
title: Stack Decorators
---

# Description

Syntax to chain several decorators using a "stack".

# Syntax

``` php
services:
    App\Mailer\Mailer:
        stack:
            - App\Mailer\LoggingMailer: ~
            - App\Mailer\RateLimitedMailer:
                arguments: [20]
            - App\Mailer\Mailer: ~
```

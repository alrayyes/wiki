---
publish: true
title: Stack Decorators
created: 2020-11-16T13:31:13
---

## Description

Syntax to chain several decorators using a "stack".

## Syntax

```php
services:
    App\Mailer\Mailer:
        stack:
            - App\Mailer\LoggingMailer: ~
            - App\Mailer\RateLimitedMailer:
                arguments: [20]
            - App\Mailer\Mailer: ~
```

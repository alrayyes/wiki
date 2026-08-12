---
publish: true
title: Service Decoration
created: 2020-11-16T13:28:26
---

# Service Decoration

## Description

How to decorate [[Symfony Services]].

## Syntax

```php
services:
    App\Mailer\Mailer: ~

    App\Mailer\RateLimitedMailer:
        decorates: App\Mailer\Mailer
        arguments: [20] # mails per second

    App\Mailer\LoggingMailer:
        decorates: App\Mailer\Mailer
```

## Changes

- [[Simpler Service Decoration]]

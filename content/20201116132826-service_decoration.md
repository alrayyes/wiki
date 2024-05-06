---
id: 06bd2b23-93a4-4e19-abfa-05ce6716b248
title: Service Decoration
---

# Description

How to decorate [services](20201112124304-symfony_services).

# Syntax

``` php
services:
    App\Mailer\Mailer: ~

    App\Mailer\RateLimitedMailer:
        decorates: App\Mailer\Mailer
        arguments: [20] # mails per second

    App\Mailer\LoggingMailer:
        decorates: App\Mailer\Mailer
```

# Changes

-   [Simpler Service
    Decoration](20201116133423-simpler_service_decoration)

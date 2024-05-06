---
id: e1692cfa-16bc-497a-aeb1-0a7468414155
title: Simpler Service Decoration
---

# Syntax

``` yaml
# config/services.yaml
services:
    App\Mailer: ~

    # Before
    App\SpecialMailer:
        decorates: App\Mailer
        arguments: ['@App\SpecialMailer.inner']

    # After
    App\SpecialMailer:
        decorates: App\Mailer
        arguments: ['@.inner']
```

---
publish: true
title: Simpler Service Decoration
created: 2020-11-16T13:34:23
modified: 2026-08-12T10:31:55.430Z
---

# Simpler Service Decoration

## Syntax

```yaml
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

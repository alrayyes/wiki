---
publish: true
title: Deprecating Service Aliases
created: 2020-11-12T12:41:59
---

# Deprecating Service Aliases

## Description

It's possible to deprecate [[Symfony Services]] aliases

## Syntax

```yaml
# config/services.yaml
services:
    # ...

    app.mailer:
        alias: App\Mail\PhpMailer
        deprecated: ~
```

### Custom error message

```yaml
# config/services.yaml
services:
  # ...

  app.mailer:
    alias: App\Mail\PhpMailer
    deprecated: 'The "%alias_id%" service alias is deprecated.'
```

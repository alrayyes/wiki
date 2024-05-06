---
id: 340acfc8-c621-4578-a588-c306ebaa4d75
title: Deprecating Service Aliases
---

# Description

It's possible to deprecate [service](20201112124304-symfony_services)
aliases

# Syntax

``` yaml
# config/services.yaml
services:
    # ...

    app.mailer:
        alias: App\Mail\PhpMailer
        deprecated: ~
```

## Custom error message

``` yaml
# config/services.yaml
services:
  # ...

  app.mailer:
    alias: App\Mail\PhpMailer
    deprecated: 'The "%alias_id%" service alias is deprecated.'
```

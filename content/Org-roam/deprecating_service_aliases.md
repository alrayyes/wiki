---
publish: true
title: Deprecating Service Aliases
created: 2020-11-12T12:41:59
modified: 2026-08-05T10:26:50.498Z
---

# Deprecating Service Aliases

# Description

It's possible to deprecate \[Symfony Services]\(Symfony Services) aliases

# Syntax

# config/services.yaml

services:
\# ...

```
app.mailer:
    alias: App\Mail\PhpMailer
    deprecated: ~
```

## Custom error message

# config/services.yaml

services:

# ...

app.mailer:
alias: App\Mail\PhpMailer
deprecated: 'The "%alias\_id%" service alias is deprecated.'

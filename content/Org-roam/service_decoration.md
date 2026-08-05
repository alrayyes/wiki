---
publish: true
title: Service Decoration
created: 2020-11-16T13:28:26
modified: 2026-08-05T07:58:56.709Z
---

# Service Decoration

# Description

How to decorate \[Symfony Services]\(Symfony Services).

# Syntax

services:
App\Mailer\Mailer: ~

```
App\Mailer\RateLimitedMailer:
    decorates: App\Mailer\Mailer
    arguments: [20] # mails per second

App\Mailer\LoggingMailer:
    decorates: App\Mailer\Mailer
```

# Changes

- \[Simpler Service Decoration]\(Simpler Service Decoration)

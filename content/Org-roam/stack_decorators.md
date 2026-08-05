---
publish: true
title: Stack Decorators
created: 2020-11-16T13:31:13
modified: 2026-08-05T07:58:56.710Z
---

# Stack Decorators

# Description

Syntax to chain several decorators using a "stack".

# Syntax

services:
App\Mailer\Mailer:
stack:
\- App\Mailer\LoggingMailer: ~
\- App\Mailer\RateLimitedMailer:
arguments: \[20]
\- App\Mailer\Mailer: ~

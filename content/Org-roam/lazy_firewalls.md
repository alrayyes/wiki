---
publish: true
title: Lazy Firewalls
created: 2020-11-13T18:30:38
modified: 2026-08-05T10:26:50.509Z
---

# Lazy Firewalls

# Syntax

# config/packages/security.yaml

security:
\# ...
firewalls:
main:
pattern: ^/
anonymous: lazy
\# ...

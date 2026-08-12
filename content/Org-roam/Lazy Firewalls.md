---
publish: true
title: Lazy Firewalls
created: 2020-11-13T18:30:38
modified: 2026-08-12T09:44:58.340Z
---

# Lazy Firewalls

## Syntax

```yaml
# config/packages/security.yaml
security:
    # ...
    firewalls:
        main:
            pattern: ^/
            anonymous: lazy
            # ...
```

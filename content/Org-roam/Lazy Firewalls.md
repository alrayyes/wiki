---
publish: true
title: Lazy Firewalls
created: 2020-11-13T18:30:38
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

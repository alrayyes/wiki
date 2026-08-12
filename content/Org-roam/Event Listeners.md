---
publish: true
title: Event Listeners
created: 2020-11-13T17:55:27
modified: 2026-08-12T10:31:55.397Z
---

# Event Listeners

## Syntax

### Pre Symfony 5.0

```yaml
# config/services.yaml
services:
    tags:
      - { name: kernel.event_listener, event: kernel.request }
```

### Symfony 5.0

[[Simpler Event Listeners]]

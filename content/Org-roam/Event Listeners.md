---
publish: true
title: Event Listeners
created: 2020-11-13T17:55:27
---

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

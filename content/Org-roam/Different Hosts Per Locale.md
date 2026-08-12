---
publish: true
title: Different Hosts Per Locale
created: 2020-11-16T13:36:27
modified: 2026-08-12T10:31:55.394Z
---

# Different Hosts Per Locale

## Syntax

```yaml
# config/routes/annotations.yaml
controllers:
    resource: '../../src/Controller/'
    type: annotation
    host:
        fr: www.example.fr
        en: www.example.com
```

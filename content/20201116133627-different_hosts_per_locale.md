---
id: b354b12a-af0e-45cd-9c7b-030ba412cb8d
title: Different Hosts Per Locale
---

# Syntax

``` yaml
# config/routes/annotations.yaml
controllers:
    resource: '../../src/Controller/'
    type: annotation
    host:
        fr: www.example.fr
        en: www.example.com
```

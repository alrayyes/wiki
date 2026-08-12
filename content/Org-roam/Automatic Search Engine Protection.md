---
publish: true
title: Automatic Search Engine Protection
created: 2020-11-12T12:48:32
modified: 2026-08-12T09:32:15.595Z
---

# Automatic Search Engine Protection

## Description

Symfony dissalows search engine indexing for development applications. A ~X-Robots-Tag: noindex~ HTTP header is added to all responses. This can be manually overridden in the config.

## Syntax

```yaml
# config/packages/framework.yaml
framework:
    # ...
    disallow_search_engine_index: false
```

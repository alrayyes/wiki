---
id: c6744b2e-f845-4ac7-83d5-ef206743e4a6
title: Automatic Search Engine Protection
---

# Description

Symfony dissalows search engine indexing for development applications. A
`X-Robots-Tag: noindex` HTTP header is added to all responses. This can
be manually overridden in the config.

# Syntax

``` yaml
# config/packages/framework.yaml
framework:
    # ...
    disallow_search_engine_index: false
```

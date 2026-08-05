---
publish: true
title: Automatic Search Engine Protection
created: 2020-11-12T12:48:32
modified: 2026-08-05T07:58:56.672Z
---

# Automatic Search Engine Protection

# Description

Symfony dissalows search engine indexing for development applications. A ~X-Robots-Tag: noindex~ HTTP header is added to all responses. This can be manually overridden in the config.

# Syntax

# config/packages/framework.yaml

framework:
\# ...
disallow\_search\_engine\_index: false

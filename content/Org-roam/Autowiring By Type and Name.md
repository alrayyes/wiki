---
publish: true
title: Autowiring By Type and Name
created: 2020-11-11T10:48:14
modified: 2026-08-12T09:44:58.313Z
---

# Autowiring By Type and Name

## Introduction

Since [[Symfony 4.2]], services can now be bound by type and name.

## Syntax

```yaml
# config/services.yaml
services:
    _defaults:
        bind:
            # it works with scalar types too (string, int, array, etc.)
            string $adminEmail: 'manager@example.com'

            # but it's mostly used with classes
            Psr\Log\LoggerInterface $requestLogger: '@monolog.logger.request'
```

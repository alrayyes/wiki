---
id: 5d2da6a0-e612-41f3-9ac7-756a541dc8e8
title: Autowiring By Type and Name
---

# Introduction

Since [Symfony 4.2](20201111101706-symfony_4_2), services can now be
bound by type and name.

# Syntax

``` yaml
# config/services.yaml
services:
    _defaults:
        bind:
            # it works with scalar types too (string, int, array, etc.)
            string $adminEmail: 'manager@example.com'

            # but it's mostly used with classes
            Psr\Log\LoggerInterface $requestLogger: '@monolog.logger.request'
```

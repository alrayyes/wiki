---
publish: true
title: name_prefix
created: 2020-11-10T15:33:51
modified: 2026-08-12T09:44:58.341Z
---

# name\_prefix

## Introduction

This is an option to prefix the named of the routes imported in configuration files.

## Syntax

```yaml
app:
    resource: ../controller/routing.yaml

api:
    resource: ../controller/routing.yaml
    # this prefix is added to all the action route names
    name_prefix: api_
    # this prefix is added to all the action URLs
    prefix: /api
```

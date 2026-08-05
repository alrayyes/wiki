---
publish: true
title: name_prefix
created: 2020-11-10T15:33:51
modified: 2026-08-05T07:58:56.698Z
---

# name\_prefix

# Introduction

This is an option to prefix the named of the routes imported in configuration files.

# Syntax

app:
resource: ../controller/routing.yaml

api:
resource: ../controller/routing.yaml
\# this prefix is added to all the action route names
name\_prefix: api\_
\# this prefix is added to all the action URLs
prefix: /api

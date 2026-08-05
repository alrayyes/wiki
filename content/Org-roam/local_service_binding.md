---
publish: true
title: Local Service Binding
created: 2020-11-09T15:31:59
modified: 2026-08-05T10:26:50.509Z
---

# Local Service Binding

# Introduction

Since \[Symfony 4.0]\(Symfony 4.0) autowiring scalar arguments has been simplified with local binding:

# Syntax

## Pre Symfony 4.0

services:
\_defaults:
autowire: true
autoconfigure: true
public: false

```
App\Some\Service1:
    $projectDir: '%kernel.project_dir%'

App\Some\Service2:
    $projectDir: '%kernel.project_dir%'

App\Some\Service3:
    $projectDir: '%kernel.project_dir%'
```

## Post Symfony 4.0

services:
\_defaults:
autowire: true
autoconfigure: true
public: false
bind:
\$projectDir: '%kernel.project\_dir%'

## Explicitly define injection services

# when services created/defined in this file inject 'BarInterface',

# use the '@normal\_bar\_service' ...

services:
\_defaults:
bind:
BarInterface: "@normal\_bar\_service"

# ... except for this particular service, which uses a different service

Foo:
bind:
BarInterface: "@special\_bar\_service"

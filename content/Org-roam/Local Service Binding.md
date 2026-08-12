---
publish: true
title: Local Service Binding
created: 2020-11-09T15:31:59
---

## Introduction

Since [[Symfony 4.0]] autowiring scalar arguments has been simplified with local binding:

## Syntax

### Pre Symfony 4.0

```yaml
services:
    _defaults:
        autowire: true
        autoconfigure: true
        public: false

    App\Some\Service1:
        $projectDir: '%kernel.project_dir%'

    App\Some\Service2:
        $projectDir: '%kernel.project_dir%'

    App\Some\Service3:
        $projectDir: '%kernel.project_dir%'

```

### Post Symfony 4.0

```yaml
services:
    _defaults:
        autowire: true
        autoconfigure: true
        public: false
        bind:
            $projectDir: '%kernel.project_dir%'

```

### Explicitly define injection services

```yaml
# when services created/defined in this file inject 'BarInterface',
# use the '@normal_bar_service' ...
services:
  _defaults:
    bind:
      BarInterface: "@normal_bar_service"

  # ... except for this particular service, which uses a different service
  Foo:
    bind:
      BarInterface: "@special_bar_service"
```

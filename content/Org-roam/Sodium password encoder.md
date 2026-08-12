---
publish: true
title: Sodium password encoder
created: 2020-11-12T13:37:36
---

## Description

In Symfony 4.3, the [[Symfony Argon2i Password Hasher]] is deprecated. ~SodiumPasswordEncoder~ is used instead. Best practice since [[Symfony 4.3]] is to use the [[Symfony Native Encoder]].

## Syntax

```yaml
# config/packages/security.yml
security:
  # ...
  encoders:
    App\Entity\User:
      algorithm: sodium
```

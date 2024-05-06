---
id: 7cc0b66c-a7df-48c7-9caf-f934f159112d
title: Symfony Argon2i Password Hasher
---

# IMPORTANT

Deprecated in [Symfony 4.3](20201112120118-symfony_4_3) and replaced
with [Sodium password
encoder](20201112133736-sodium_password_encoder)!!!

# Introduction

Added in [Symfony 4.1](20201110152518-symfony_4_1),
[Symfony](20201109140300-symfony) now supports Argon[^1] password
hashes.

# Syntax

``` yaml
# config/packages/security.yaml
security:
  # ...
  encoders:
    App\Entity\User:
      algorithm: "argon2i"
      # maximum memory (in KiB) that may be used to compute the Argon2 hash
      memory_cost: 1024
      #  number of times the Argon2 hash algorithm will be run
      time_cost: 3
```

# Footnotes

[^1]: <https://en.wikipedia.org/wiki/Argon2>

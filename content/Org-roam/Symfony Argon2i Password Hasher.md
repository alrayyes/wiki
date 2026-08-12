---
publish: true
title: Symfony Argon2i Password Hasher
created: 2020-11-10T15:27:30
modified: 2026-08-12T09:44:58.355Z
---

# Symfony Argon2i Password Hasher

## IMPORTANT

Deprecated in [[Symfony 4.3]] and replaced with [[Sodium password encoder]]!!!

## Introduction

Added in [[Symfony 4.1]], [[Symfony]] now supports Argon[^argon] password hashes.

## Syntax

```yaml
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

## Footnotes

[^argon]: https://en.wikipedia.org/wiki/Argon2

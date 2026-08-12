---
publish: true
title: Symfony Native Encoder
created: 2020-11-12T13:58:51
modified: 2026-08-12T09:44:58.357Z
---

# Symfony Native Encoder

## Description

This is best practice since [[Symfony 4.3]].

This value auto-selects the best possible hashing algorithm, so it doesn't refer to an specific algorithm and it will change in the future. The current implementation uses ~'sodium'~ if possible and otherwise, it falls back to ~'native'~.

The ~'native'~ config option is associated with the ~NativePasswordEncoder~ class, which is the other main change about password hashers in Symfony 4.3. This new encoder relies both on Symfony and PHP to select the best possible algorithm.

The current ~NativePasswordEncoder~ implementation tries to use any of the Argon2 variants (Argon2i or Argon2id) before falling back to Bcrypt. However, if the ~PASSWORD\_DEFAULT~ PHP constant changes in the future, that new algorithm will be selected (if PHP defines it as stronger than Argon2).

## Syntax

```yaml
# config/packages/security.yml
security:
  # ...
  encoders:
    App\Entity\User:
      algorithm: auto
```

## Changes

- [[Password Migrations]]

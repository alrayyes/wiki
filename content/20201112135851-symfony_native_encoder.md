---
id: cd2d3da1-7251-49f1-939b-460c92ba317b
title: Symfony Native Encoder
---

# Description

This is best practice since [Symfony 4.3](20201112120118-symfony_4_3).

This value auto-selects the best possible hashing algorithm, so it
doesn't refer to an specific algorithm and it will change in the future.
The current implementation uses `'sodium'` if possible and otherwise, it
falls back to `'native'`.

The `'native'` config option is associated with the
`NativePasswordEncoder` class, which is the other main change about
password hashers in Symfony 4.3. This new encoder relies both on Symfony
and PHP to select the best possible algorithm.

The current `NativePasswordEncoder` implementation tries to use any of
the Argon2 variants (Argon2i or Argon2id) before falling back to Bcrypt.
However, if the `PASSWORD_DEFAULT` PHP constant changes in the future,
that new algorithm will be selected (if PHP defines it as stronger than
Argon2).

# Syntax

``` yaml
# config/packages/security.yml
security:
  # ...
  encoders:
    App\Entity\User:
      algorithm: auto
```

# Changes

-   [Password Migrations](20201113181759-password_migrations)

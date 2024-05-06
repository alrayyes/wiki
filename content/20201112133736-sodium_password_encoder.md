---
id: ebc9cf71-62ed-44fa-98c6-b2d01fbd69fe
title: Sodium password encoder
---

# Description

In Symfony 4.3, the [Symfony Argon2i Password
Hasher](20201110152730-symfony_argon2i_password_hasher) is deprecated.
`SodiumPasswordEncoder` is used instead. Best practice since [Symfony
4.3](20201112120118-symfony_4_3) is to use the [native
encoder](20201112135851-symfony_native_encoder).

# Syntax

``` yaml
# config/packages/security.yml
security:
  # ...
  encoders:
    App\Entity\User:
      algorithm: sodium
```

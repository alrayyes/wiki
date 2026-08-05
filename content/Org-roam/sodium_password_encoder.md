---
publish: true
title: Sodium password encoder
created: 2020-11-12T13:37:36
modified: 2026-08-05T07:58:56.709Z
---

# Sodium password encoder

# Description

In Symfony 4.3, the \[Symfony Argon2i Password Hasher]\(Symfony Argon2i Password Hasher) is deprecated. ~SodiumPasswordEncoder~ is used instead. Best practice since \[Symfony 4.3]\(Symfony 4.3) is to use the \[Symfony Native Encoder]\(Symfony Native Encoder).

# Syntax

# config/packages/security.yml

security:

# ...

encoders:
App\Entity\User:
algorithm: sodium

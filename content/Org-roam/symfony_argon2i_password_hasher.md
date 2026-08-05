---
publish: true
title: Symfony Argon2i Password Hasher
created: 2020-11-10T15:27:30
modified: 2026-08-05T10:26:50.517Z
---

# Symfony Argon2i Password Hasher

# IMPORTANT

Deprecated in \[Symfony 4.3]\(Symfony 4.3) and replaced with \[Sodium password encoder]\(Sodium password encoder)!!!

# Introduction

Added in \[Symfony 4.1]\(Symfony 4.1), [Symfony](Symfony) now supports Argon\[fn:argon] password hashes.

# Syntax

# config/packages/security.yaml

security:

# ...

encoders:
App\Entity\User:
algorithm: "argon2i"
\# maximum memory (in KiB) that may be used to compute the Argon2 hash
memory\_cost: 1024
\#  number of times the Argon2 hash algorithm will be run
time\_cost: 3

# Footnotes

\[fn:argon]https://en.wikipedia.org/wiki/Argon2

---
publish: true
title: Ecrypted Secrets Management
created: 2020-11-13T17:44:44
modified: 2026-08-05T10:26:50.499Z
---

# Ecrypted Secrets Management

# Description

Encryption based feature to manage secrets.

# Steps

## 1. Generate keys to encrypt/decrypt secret

Uses libsodium\[fn:libsodium] and public key cryptography.

php bin/console secrets:generate-keys

## 2. Upload private key

Upload the private key to your remote server using SSH or any other safe means and store it in the same ~config/secrets/<environment>/~ directory.

## 3. Create a new secret to store the contents

php bin/console secrets:set DATABASE\_URL

Please type the secret value:
##############

\[OK] Secret "DATABASE\_URL" encrypted in "config/secrets/dev/"
you can commit it.

# Using secret

Use this new secret as any other normal env var in your configuration files and Symfony will decrypt the value transparently when needed.

# config/packages/doctrine.yaml

doctrine:
dbal:
url: "%env(DATABASE\_URL)%"
\# ...

# Footnotes

\[fn:libsodium]https://download.libsodium.org/doc/

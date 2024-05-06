---
id: e9ea6e53-c383-4b23-b90c-77cd202f8002
title: Ecrypted Secrets Management
---

# Description

Encryption based feature to manage secrets.

# Steps

## 1. Generate keys to encrypt/decrypt secret

Uses libsodium[^1] and public key cryptography.

``` shell
php bin/console secrets:generate-keys
```

## 2. Upload private key

Upload the private key to your remote server using SSH or any other safe
means and store it in the same `config/secrets/<environment>/`
directory.

## 3. Create a new secret to store the contents

``` shell
php bin/console secrets:set DATABASE_URL

Please type the secret value:
**************

[OK] Secret "DATABASE_URL" encrypted in "config/secrets/dev/"
you can commit it.
```

# Using secret

Use this new secret as any other normal env var in your configuration
files and Symfony will decrypt the value transparently when needed.

``` yaml
# config/packages/doctrine.yaml
doctrine:
    dbal:
        url: "%env(DATABASE_URL)%"
        # ...
```

# Footnotes

[^1]: <https://download.libsodium.org/doc/>

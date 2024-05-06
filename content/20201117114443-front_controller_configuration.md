---
id: ad565d8b-8c81-45a0-9a4a-7c17feb8733e
title: Front Controller Configuration
---

# Description

Front controller behaviour can be configured using configuration
options. Pre PHP 7.4 there was a 20% penalty of doing this vs editing
the `index.php` file. However, PHP preloading[^1] negates this. Post PHP
7.4 configuration options can be used without a performance penalty.

# Syntax

``` yaml
# config/packages/framework.yaml
framework:
    # use the HTTP Cache defaults
    http_cache: true

    # configure every HTTP Cache option
    http_cache:
        private_headers: ['Authorization', 'Cookie', 'MyCustomHeader']
        default_ttl: 3600
        allow_revalidate: true
        stale_if_error: 600

    # configure proxies to trust directly in the config file:
    trusted_proxies: '127.0.0.0/8,10.0.0.0/8,172.16.0.0/12,192.168.0.0/16'
    # or use an env var if this value is dynamic
    trusted_proxies: '%env(TRUSTED_PROXIES)%'

    # you can also define the trusted headers
    trusted_headers: ['x-forwarded-all', '!x-forwarded-host', '!x-forwarded-prefix']
```

# Footnotes

[^1]: <https://www.php.net/manual/en/opcache.preloading.php>

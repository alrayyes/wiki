---
publish: true
title: ROLE_PREVIOUS_ADMIN
created: 2020-11-16T12:21:25
---

# ROLE\_PREVIOUS\_ADMIN

## Description

Shows that currently logged in user is impersonating another user

## Syntax

```php
{% if is_granted('ROLE_PREVIOUS_ADMIN') %}
    <a href="...">Exit impersonation</a>
{% endif %}
```

## Deprecation

Deprecated in [[Symfony 5.1]], replaced with [[IS_IMPERSONATOR]].

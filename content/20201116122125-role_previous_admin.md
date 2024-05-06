---
id: bc9f093c-3ae9-44ca-bf33-b8c262bd1f55
title: ROLE~PREVIOUSADMIN~
---

# Description

Shows that currently logged in user is impersonating another user

# Syntax

``` php
{% if is_granted('ROLE_PREVIOUS_ADMIN') %}
    <a href="...">Exit impersonation</a>
{% endif %}
```

# Deprecation

Deprecated in [Symfony 5.1](20201116105919-symfony_5_1), replaced with
[IS~IMPERSONATOR~](20201116122525-is_impersonator).

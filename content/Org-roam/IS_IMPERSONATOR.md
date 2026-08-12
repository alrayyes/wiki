---
publish: true
title: IS_IMPERSONATOR
created: 2020-11-16T12:25:25
---

## Description

Replacement for [[ROLE_PREVIOUS_ADMIN]]

## Syntax

```php
{# BEFORE #}
{% if is_granted('ROLE_PREVIOUS_ADMIN') %}
    <a href="...">Exit impersonation</a>
{% endif %}

{# AFTER #}
{% if is_granted('IS_IMPERSONATOR') %}
    <a href="...">Exit impersonation</a>
{% endif %}

```

---
publish: true
title: IS_REMEMBERED
created: 2020-11-16T12:17:59
---

## Description

Checks if user is a "Remember Me" user. Replaces [[IS_AUTHENTICATED_FULLY]] & [[IS_AUTHENTICATED_REMEMBERED]]

## Syntax

```php
// BEFORE
if ($this->isGranted('IS_AUTHENTICATED_REMEMBERED')
    && !$this->isGranted('IS_AUTHENTICATED_FULLY')) {
    // ...
}

// AFTER
if ($this->isGranted('IS_REMEMBERED')) {
    // ...
}
```

```twig
{# BEFORE #}
{% if is_granted('IS_AUTHENTICATED_ANONYMOUSLY')
    and not is_granted('IS_AUTHENTICATED_REMEMBERED')
    and not is_granted('IS_AUTHENTICATED_FULLY') %}
    {# ... #}
{% endif %}

{# AFTER #}
{% if is_granted('IS_ANONYMOUS') %}
    {# ... #}
{% endif %}
```

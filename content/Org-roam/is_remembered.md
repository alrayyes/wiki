---
publish: true
title: IS_REMEMBERED
created: 2020-11-16T12:17:59
modified: 2026-08-05T07:58:56.687Z
---

# IS\_REMEMBERED

# Description

Checks if user is a "Remember Me" user. Replaces [IS\_AUTHENTICATED\_FULLY](IS_AUTHENTICATED_FULLY) & [IS\_AUTHENTICATED\_REMEMBERED](IS_AUTHENTICATED_REMEMBERED)

# Syntax

// BEFORE
if ($this->isGranted('IS_AUTHENTICATED_REMEMBERED')
    && !$this->isGranted('IS\_AUTHENTICATED\_FULLY')) {
// ...
}

// AFTER
if (\$this->isGranted('IS\_REMEMBERED')) {
// ...
}

{# BEFORE #}
{% if is\_granted('IS\_AUTHENTICATED\_ANONYMOUSLY')
and not is\_granted('IS\_AUTHENTICATED\_REMEMBERED')
and not is\_granted('IS\_AUTHENTICATED\_FULLY') %}
{# ... #}
{% endif %}

{# AFTER #}
{% if is\_granted('IS\_ANONYMOUS') %}
{# ... #}
{% endif %}

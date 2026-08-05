---
publish: true
title: IS_IMPERSONATOR
created: 2020-11-16T12:25:25
modified: 2026-08-05T07:58:56.687Z
---

# IS\_IMPERSONATOR

# Description

Replacement for [ROLE\_PREVIOUS\_ADMIN](ROLE_PREVIOUS_ADMIN)

# Syntax

{# BEFORE #}
{% if is\_granted('ROLE\_PREVIOUS\_ADMIN') %} <a href="...">Exit impersonation</a>
{% endif %}

{# AFTER #}
{% if is\_granted('IS\_IMPERSONATOR') %} <a href="...">Exit impersonation</a>
{% endif %}

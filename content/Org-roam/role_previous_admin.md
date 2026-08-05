---
publish: true
title: ROLE_PREVIOUS_ADMIN
created: 2020-11-16T12:21:25
modified: 2026-08-05T10:26:50.514Z
---

# ROLE\_PREVIOUS\_ADMIN

# Description

Shows that currently logged in user is impersonating another user

# Syntax

{% if is\_granted('ROLE\_PREVIOUS\_ADMIN') %} <a href="...">Exit impersonation</a>
{% endif %}

# Deprecation

Deprecated in \[Symfony 5.1]\(Symfony 5.1), replaced with [IS\_IMPERSONATOR](IS_IMPERSONATOR).

---
publish: true
title: priority
created: 2020-11-16T14:37:40
modified: 2026-08-05T07:58:56.704Z
---

# priority

# Description

Grants or denies access depending on the first voter that does not abstain. In this case, the voter priority is essential, because the first non-abstain decision will be the final decision:

# Syntax

# config/packages/security.yaml

security:
access\_decision\_manager:
strategy: priority
\# ...

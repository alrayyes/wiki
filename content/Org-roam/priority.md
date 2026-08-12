---
publish: true
title: priority
created: 2020-11-16T14:37:40
---

## Description

Grants or denies access depending on the first voter that does not abstain. In this case, the voter priority is essential, because the first non-abstain decision will be the final decision:

## Syntax

```yaml
# config/packages/security.yaml
security:
    access_decision_manager:
        strategy: priority
        # ...
```

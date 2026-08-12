---
publish: true
title: trigger_depcreation
created: 2020-11-16T14:09:34
---

## Syntax

```php
// Before
@trigger_error(
    'Not setting the "framework.router.utf8" configuration option is deprecated
    since Symfony 5.1, it will default to "true" in Symfony 6.0.',
    E_USER_DEPRECATED
);

// After
trigger_deprecation(
    'symfony/framework-bundle', '5.1',
    'Not setting the "framework.router.utf8" configuration option is deprecated,
    it will default to "true" in version 6.0.'
);
```

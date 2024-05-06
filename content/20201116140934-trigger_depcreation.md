---
id: d6b8e744-b6f2-41aa-a3c9-c4d366ca5eca
title: trigger~depcreation~
---

# Syntax

``` php
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

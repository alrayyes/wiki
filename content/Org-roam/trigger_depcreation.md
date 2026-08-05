---
publish: true
title: trigger_depcreation
created: 2020-11-16T14:09:34
modified: 2026-08-05T10:26:50.519Z
---

# trigger\_depcreation

# Syntax

// Before
@trigger\_error(
'Not setting the "framework.router.utf8" configuration option is deprecated
since Symfony 5.1, it will default to "true" in Symfony 6.0.',
E\_USER\_DEPRECATED
);

// After
trigger\_deprecation(
'symfony/framework-bundle', '5.1',
'Not setting the "framework.router.utf8" configuration option is deprecated,
it will default to "true" in version 6.0.'
);

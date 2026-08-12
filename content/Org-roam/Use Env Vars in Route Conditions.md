---
publish: true
title: Use Env Vars in Route Conditions
created: 2020-11-16T13:16:33
modified: 2026-08-12T10:26:13.214Z
---

# Use Env Vars in Route Conditions

## Syntax

```php
/**
 * @Route("/new-feature", condition="env('bool:IS_FEATURE_ENABLED') === true")
 */
public function __invoke()
{
    // this route will only execute when the value of the
    // IS_FEATURE_ENABLED env var is TRUE
}
```

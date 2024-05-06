---
id: c7ac91f7-12f3-4c6c-b552-ba05c5206be9
title: Use Env Vars in Route Conditions
---

# Syntax

``` php
/**
 * @Route("/new-feature", condition="env('bool:IS_FEATURE_ENABLED') === true")
 */
public function __invoke()
{
    // this route will only execute when the value of the
    // IS_FEATURE_ENABLED env var is TRUE
}
```

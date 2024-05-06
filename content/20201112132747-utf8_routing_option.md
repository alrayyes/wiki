---
id: 45b1f81a-d5f4-4f28-99d6-6a1592c75f7d
title: UTF8 Routing Option
---

# Syntax

``` php
// PHP Annotations

/**
 * @Route("/category/{name}", name="category", utf8=true)
 */
public function category()
```

``` yaml
category:
  path:     /category/{name}
  controller: App\Controller\DefaultController::category
    utf8: true
```

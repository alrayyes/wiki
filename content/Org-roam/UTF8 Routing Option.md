---
publish: true
title: UTF8 Routing Option
created: 2020-11-12T13:27:47
modified: 2026-08-12T09:32:15.644Z
---

# UTF8 Routing Option

## Syntax

```php
// PHP Annotations

/**
 * @Route("/category/{name}", name="category", utf8=true)
 */
public function category()
```

```yaml
category:
  path:     /category/{name}
  controller: App\Controller\DefaultController::category
    utf8: true
```

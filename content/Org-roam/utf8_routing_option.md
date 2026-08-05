---
publish: true
title: UTF8 Routing Option
created: 2020-11-12T13:27:47
modified: 2026-08-05T10:26:50.521Z
---

# UTF8 Routing Option

# Syntax

// PHP Annotations

/\*\*

- @Route("/category/{name}", name="category", utf8=true)
  \*/
  public function category()

category:
path:     /category/{name}
controller: App\Controller\DefaultController::category
utf8: true

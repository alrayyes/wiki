---
publish: true
title: Required
created: 2020-11-17T11:17:57
modified: 2026-08-05T07:58:56.706Z
---

# Required

# Description

Attribute replacement for [@required](@required).

# Syntax

use Symfony\Contracts\Service\Attribute\Required;

class SomeService
{
\#\[Required]
public Bar \$bar;

```
#[Required]
public function setFoo(Foo $foo): void
{
    // ...
}
```

}

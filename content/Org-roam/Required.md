---
publish: true
title: Required
created: 2020-11-17T11:17:57
modified: 2026-08-12T10:26:13.196Z
---

# Required

## Description

Attribute replacement for [[@required]].

## Syntax

```php
use Symfony\Contracts\Service\Attribute\Required;

class SomeService
{
    #[Required]
    public Bar $bar;

    #[Required]
    public function setFoo(Foo $foo): void
    {
        // ...
    }
}
```

---
publish: true
title: PHP Union Type
created: 2020-11-09T13:39:23
modified: 2026-08-12T09:32:15.627Z
---

# PHP Union Type

## Description

Allows multiple possible types[^rc] to be given to a parameter/member.

## Syntax

```php
class Example {
    private int|float $foo;

    public function __construct(int|float $foo) {
        $this->foo = $foo;
    }

    public function doSomethingWithMultipleTypes(float|int $bar): int|float {
        return ($bar + $this->foo) * 2;
    }
}
```

## Inheritance

```php
class A{
    public function foo(string|int $foo): string|int {}
}

class B extends A{
    public function foo(string|int|float $foo): string {}
}
```

## Footnotes

[^rfc]: https://wiki.php.net/rfc/union_types_v2

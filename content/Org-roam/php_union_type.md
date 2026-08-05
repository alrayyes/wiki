---
publish: true
title: PHP Union Type
created: 2020-11-09T13:39:23
modified: 2026-08-05T10:26:50.512Z
---

# PHP Union Type

- [Description](#description)
- [Syntax](#syntax)
- [Inheritance](#inheritance)
- [Footnotes](#footnotes)

# Description

Allows multiple possible types\[fn:rc] to be given to a parameter/member.

# Syntax

class Example {
private int|float \$foo;

```
public function __construct(int|float $foo) {
    $this->foo = $foo;
}

public function doSomethingWithMultipleTypes(float|int $bar): int|float {
    return ($bar + $this->foo) * 2;
}
```

}

# Inheritance

class A{
public function foo(string|int \$foo): string|int {}
}

class B extends A{
public function foo(string|int|float \$foo): string {}
}

# Footnotes

\[fn:rfc]https://wiki.php.net/rfc/union\_types\_v2

---
publish: true
title: PHP Attributes
created: 2020-11-10T10:04:20
modified: 2026-08-05T10:26:50.511Z
---

# PHP Attributes

# Description

Introduced in \[PHP 8.0]\(PHP 8.0). Attributes\[fn:attributes] are a way to add metadata to classes. Stitcher\[fn:stitcher] has an article that goes in depth.

# Syntax

use App\Attributes\ExampleAttribute;

\#\[ExampleAttribute]
class Foo
{
\#\[ExampleAttribute]
public const FOO = 'foo';

```
#[ExampleAttribute]
public $x;

#[ExampleAttribute]
public function foo(#[ExampleAttribute] $bar) { }
```

}

\#\[Attribute]
class ExampleAttribute
{
public \$value;

```
public function __construct($value)
{
    $this->value = $value;
}
```

}

# Footnotes

\[fn:attributes]https://wiki.php.net/rfc/attributes
\[fn:stitcher]https://stitcher.io/blog/attributes-in-php-8

---
publish: true
title: PHP Attributes
created: 2020-11-10T10:04:20
modified: 2026-08-12T09:44:58.343Z
---

# PHP Attributes

## Description

Introduced in [[PHP 8.0]]. Attributes[^attributes] are a way to add metadata to classes. Stitcher[^stitcher] has an article that goes in depth.

## Syntax

```php
use App\Attributes\ExampleAttribute;

#[ExampleAttribute]
class Foo
{
    #[ExampleAttribute]
    public const FOO = 'foo';

    #[ExampleAttribute]
    public $x;

    #[ExampleAttribute]
    public function foo(#[ExampleAttribute] $bar) { }
}
```

```php
#[Attribute]
class ExampleAttribute
{
    public $value;

    public function __construct($value)
    {
        $this->value = $value;
    }
}

```

## Footnotes

[^attributes]: https://wiki.php.net/rfc/attributes

[^stitcher]: https://stitcher.io/blog/attributes-in-php-8

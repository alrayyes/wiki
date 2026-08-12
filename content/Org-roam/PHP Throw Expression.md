---
publish: true
title: PHP Throw Expression
created: 2020-11-11T10:08:07
---

## Description

Since [[PHP 8.0]], ~throw~ can also be used as an expression[^throw].

## Syntax

```php
// This was previously not possible since arrow functions only accept a single expression while throw was a statement.
$callable = fn() => throw new Exception();

// $value is non-nullable.
$value = $nullableValue ?? throw new InvalidArgumentException();

// $value is truthy.
$value = $falsableValue ?: throw new InvalidArgumentException();

// $value is only set if the array is not empty.
$value = !empty($array)
    ? reset($array)
    : throw new InvalidArgumentException();

$condition && throw new Exception();
$condition || throw new Exception();
$condition and throw new Exception();
$condition or throw new Exception();
```

## Footnotes

[^throw]: https://wiki.php.net/rfc/throw_expression

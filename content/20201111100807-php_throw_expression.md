---
id: d4bcfd55-088e-4658-9e7b-5429f7ec060f
title: PHP Throw Expression
---

# Description

Since [PHP 8.0](20201109133834-php_8_0), `throw` can also be used as an
expression[^1].

# Syntax

``` php
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

# Footnotes

[^1]: <https://wiki.php.net/rfc/throw_expression>

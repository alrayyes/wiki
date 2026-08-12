---
publish: true
title: get_debug_type()
created: 2020-11-13T11:59:39
---

# get\_debug\_type()

## Description

Returns the variable type. Differnce with ~getttype()~ is that ~get\_debug\_type()~ is more specific. See RFC[^rfc].

## Syntax

```php
namespace Foo;

class Bar
{
}

$bar = new Bar();

echo gettype($bar)."\n"; // Object
echo get_debug_type($bar); // Foo\Bar
```

## Footnotes

[^rfc]: https://wiki.php.net/rfc/get_debug_type

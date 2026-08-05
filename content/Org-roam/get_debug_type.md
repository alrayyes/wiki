---
publish: true
title: get_debug_type()
created: 2020-11-13T11:59:39
modified: 2026-08-05T07:58:56.683Z
---

# get\_debug\_type()

# Description

Returns the variable type. Differnce with ~getttype()~ is that ~get\_debug\_type()~ is more specific. See RFC\[fn:rfc].

# Syntax

namespace Foo;

class Bar
{
}

\$bar = new Bar();

echo gettype($bar)."\n"; // Object
echo get_debug_type($bar); // Foo\Bar

# Footnotes

\[fn:rfc]https://wiki.php.net/rfc/get\_debug\_type

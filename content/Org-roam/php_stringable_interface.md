---
publish: true
title: PHP Stringable Interface
created: 2020-11-10T10:34:09
modified: 2026-08-05T07:58:56.702Z
---

# PHP Stringable Interface

# Description

Since \[PHP 8.0]\(PHP 8.0), the stringable interface\[fn:stringable] is automatically added to classes that implement the ~\_\_toString()~ method

# Syntax

class Foo
{
public function \_\_toString(): string
{
return 'foo';
}
}

function bar(string|Stringable \$stringable) { /\* … \*/ }

bar(new Foo());
bar('abc');

# Footnotes

\[fn:stringable]https://wiki.php.net/rfc/stringable

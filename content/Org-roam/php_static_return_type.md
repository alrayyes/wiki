---
publish: true
title: PHP Static Return Type
created: 2020-11-10T10:23:32
modified: 2026-08-05T10:26:50.512Z
---

# PHP Static Return Type

# Description

Introduced in \[PHP 8.0]\(PHP 8.0), static return types\[fn:staticreturntype] guarantee that a method will return an instance of its object, and not that of a parent.

# Syntax

class Foo
{
public function tralala(): static
{
return \$this;
}
}

# Footnotes

\[fn:staticreturntype]https://wiki.php.net/rfc/static\_return\_type

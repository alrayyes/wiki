---
publish: true
title: PHP Weap Maps
created: 2020-11-10T10:36:54
modified: 2026-08-05T10:26:50.512Z
---

# PHP Weap Maps

# Description

Weak maps\[fn:weakmaps] allow creating a map from objects to arbitrary values (similar to SplObjectStorage) without preventing the objects that are used as keys from being garbage collected. If an object key is garbage collected, it will simply be removed from the map. This will save a lot of headaches for people writing things like ORMs.

# Syntax

class Foo
{
private WeakMap \$cache;

```
public function getSomethingWithCaching(object $obj): object
{
    return $this->cache[$obj]
       ??= $this->computeSomethingExpensive($obj);
}
```

}

# Related

- [PHP](PHP)
- \[PHP 8.0]\(PHP 8.0)

# Footnotes

\[fn:weakmaps]https://wiki.php.net/rfc/weak\_maps

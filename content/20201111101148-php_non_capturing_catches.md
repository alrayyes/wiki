---
id: 1c3522c3-9c66-4e10-bf2d-e01807707af2
title: PHP Non-capturing Catches
---

# Description

Since [PHP 8.0](20201109133834-php_8_0), exceptions are allowed without
capturing them into variables[^1].

# Syntax

## Pre PHP8

``` php
try {
    changeImportantData();
} catch (PermissionException $ex) {
    echo "You don't have permission to do this";
}
```

## Post PHP8

``` php
try {
    changeImportantData();
} catch (PermissionException) { // The intention is clear: exception details are irrelevant
    echo "You don't have permission to do this";
}
```

# Footnotes

[^1]: <https://wiki.php.net/rfc/non-capturing_catches>

---
publish: true
title: PHP Non-capturing Catches
created: 2020-11-11T10:11:48
---

# PHP Non-capturing Catches

## Description

Since [[PHP 8.0]], exceptions are allowed without capturing them into variables[^rfc].

## Syntax

### Pre PHP8

```php
try {
    changeImportantData();
} catch (PermissionException $ex) {
    echo "You don't have permission to do this";
}
```

### Post PHP8

```php
try {
    changeImportantData();
} catch (PermissionException) { // The intention is clear: exception details are irrelevant
    echo "You don't have permission to do this";
}
```

## Footnotes

[^rfc]: https://wiki.php.net/rfc/non-capturing_catches

---
publish: true
title: PHP Non-capturing Catches
created: 2020-11-11T10:11:48
modified: 2026-08-05T07:58:56.701Z
---

# PHP Non-capturing Catches

- [Description](#description)
- [Syntax](#syntax)
  - [Pre PHP8](#pre-php8)
  - [Post PHP8](#post-php8)
- [Footnotes](#footnotes)

# Description

Since \[PHP 8.0]\(PHP 8.0), exceptions are allowed without capturing them into variables\[fn:rfc].

# Syntax

## Pre PHP8

try {
changeImportantData();
} catch (PermissionException \$ex) {
echo "You don't have permission to do this";
}

## Post PHP8

try {
changeImportantData();
} catch (PermissionException) { // The intention is clear: exception details are irrelevant
echo "You don't have permission to do this";
}

# Footnotes

\[fn:rfc]https://wiki.php.net/rfc/non-capturing\_catches

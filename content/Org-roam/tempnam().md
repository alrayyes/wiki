---
publish: true
title: tempnam()
created: 2020-11-16T14:21:05
modified: 2026-08-12T10:26:13.208Z
---

# tempnam()

## Description

Like the PHP ~tempnam()~ function this method creates a file with a unique name in the given directory.

## Syntax

```php
use Symfony\Component\Filesystem\Filesystem;

$fs = new Filesystem();

$fs->tempnam('/tmp', 'report_');         // '/tmp/report_Um3nlH'
$fs->tempnam('/tmp', 'report_', '.pdf'); // '/tmp/report_Um3nlH.pdf'
```

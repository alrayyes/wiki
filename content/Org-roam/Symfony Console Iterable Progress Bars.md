---
publish: true
title: Symfony Console Iterable Progress Bars
created: 2020-11-12T13:02:34
modified: 2026-08-12T10:26:13.205Z
---

# Symfony Console Iterable Progress Bars

## Changes

- [[iterate() method]]

## Syntax

```php
use Symfony\Component\Console\Helper\ProgressBar;

$progressBar = new ProgressBar($output);
$progressBar->start();

// ... do some work
$progressBar->advance();

// needed to ensure that the bar reaches 100%
$progressBar->finish();
```

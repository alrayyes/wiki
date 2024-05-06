---
id: b4fc3714-24f9-4eb6-9d46-3c42bdcd5be2
title: Symfony Console Iterable Progress Bars
---

# Changes

-   [iterate() method](20201112130435-iterate_method)

# Syntax

``` php
use Symfony\Component\Console\Helper\ProgressBar;

$progressBar = new ProgressBar($output);
$progressBar->start();

// ... do some work
$progressBar->advance();

// needed to ensure that the bar reaches 100%
$progressBar->finish();
```

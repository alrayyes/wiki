---
publish: true
title: Symfony Console Iterable Progress Bars
created: 2020-11-12T13:02:34
modified: 2026-08-05T10:26:50.517Z
---

# Symfony Console Iterable Progress Bars

# Changes

- \[iterate() method]\(iterate() method)

# Syntax

use Symfony\Component\Console\Helper\ProgressBar;

$progressBar = new ProgressBar($output);
\$progressBar->start();

// ... do some work
\$progressBar->advance();

// needed to ensure that the bar reaches 100%
\$progressBar->finish();

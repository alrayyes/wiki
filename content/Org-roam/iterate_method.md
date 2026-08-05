---
publish: true
title: iterate() method
created: 2020-11-12T13:04:35
modified: 2026-08-05T10:26:50.503Z
---

# iterate() method

# Syntax

\$iterable = function () {
yield 1;
yield 2;
// ...
};

use Symfony\Component\Console\Helper\ProgressBar;

$progressBar = new ProgressBar($output);

foreach ($progressBar->iterate($iterable) as \$value) {
// ... do some work
}

## Non countable variable

foreach ($progressBar->iterate($iterable, 100) as \$value) {
// ... do some work
}

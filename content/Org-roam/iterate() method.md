---
publish: true
title: iterate() method
created: 2020-11-12T13:04:35
---

# iterate() method

## Syntax

```php
$iterable = function () {
    yield 1;
    yield 2;
    // ...
};
```

```php
use Symfony\Component\Console\Helper\ProgressBar;

$progressBar = new ProgressBar($output);

foreach ($progressBar->iterate($iterable) as $value) {
    // ... do some work
}
```

### Non countable variable

```php
foreach ($progressBar->iterate($iterable, 100) as $value) {
    // ... do some work
}
```

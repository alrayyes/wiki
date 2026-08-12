---
publish: true
title: Syfmony Console Table Titles
created: 2020-11-11T10:41:24
---

## Introduction

Introduced in [[Symfony 4.2]], you can now add table titles to console output.

## Syntax

```php
use Symfony\Component\Console\Helper\Table;
 // ...

$table = new Table($output);
$table
    ->setHeaderTitle('Books')
    ->setFooterTitle('Page 1/2')
    ->setHeaders(['ISBN', 'Title', 'Author'])
    ->setRows([
        ['99921-58-10-7', 'Divine Comedy', 'Dante Alighieri'],
        // ...
    ])
;
$table->render();
```

### Set max column width

```php
// ...

// the first argument is the column position (starting from 0) and
// the second argument is the max length in characters
$table->setColumnMaxWidth(0, 5);
$table->setColumnMaxWidth(1, 10);
$table->render();
```

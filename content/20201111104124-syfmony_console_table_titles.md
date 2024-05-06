---
id: a0217544-b988-4292-9c8d-003bdafb766b
title: Syfmony Console Table Titles
---

# Introduction

Introduced in [Symfony 4.2](20201111101706-symfony_4_2), you can now add
table titles to console output.

# Syntax

``` php
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

## Set max column width

``` php
// ...

// the first argument is the column position (starting from 0) and
// the second argument is the max length in characters
$table->setColumnMaxWidth(0, 5);
$table->setColumnMaxWidth(1, 10);
$table->render();
```

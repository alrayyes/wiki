---
id: 1b9bdd03-0b2c-4ed1-8bf5-fe9169b434b3
title: Single Command Applications
---

# Syntax

``` php
#!/usr/bin/env php
<?php
require __DIR__.'/vendor/autoload.php';

use Symfony\Component\Console\Input\InputInterface;
use Symfony\Component\Console\Output\OutputInterface;

use Symfony\Component\Console\SingleCommandApplication;

(new SingleCommandApplication())
    ->setCode(function (InputInterface $input, OutputInterface $output) {

        // add here the code of your console command...

    })
    ->run();
```

``` php
// ...
use Symfony\Component\Console\Input\InputArgument;
use Symfony\Component\Console\Input\InputOption;

use Symfony\Component\Console\SingleCommandApplication;

(new SingleCommandApplication())
    ->setName('My Super Command')
    ->setVersion('1.0.0')
    ->setHelp('This command allows you to...')
    ->addArgument('foo', InputArgument::OPTIONAL, 'The directory')
    ->addOption('bar', null, InputOption::VALUE_REQUIRED)
    ->setCode(function (InputInterface $input, OutputInterface $output) {

        // ...

    })
    ->run();
```

---
publish: true
aliases:
  - Command::SUCCESS
title: Command::SUCCESS
created: 2020-11-16T14:16:57
modified: 2026-08-12T09:32:15.598Z
---

# Command::SUCCESS

## Description

SUCCESS constant to be used as command exit code

## Syntax

```php
// src/Command/CreateUserCommand.php
namespace App\Command;

use Symfony\Component\Console\Command\Command;
use Symfony\Component\Console\Input\InputInterface;
use Symfony\Component\Console\Output\OutputInterface;

class CreateUserCommand extends Command
{
    protected static $defaultName = 'app:create-user';

    // ...

    protected function execute(InputInterface $input, OutputInterface $output)
    {
        // ...

        // Before
        return 0;

        // After
        return Command::SUCCESS;
    }
}
```

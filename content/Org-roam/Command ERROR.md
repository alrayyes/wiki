---
publish: true
aliases:
  - Command::ERROR
title: Command::ERROR
created: 2020-11-16T14:18:17
---

## Description

ERROR constant to be used as command exit code

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
        return Command::ERROR;
    }
}
```

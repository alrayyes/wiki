---
publish: true
title: Command::ERROR
created: 2020-11-16T14:18:17
modified: 2026-08-05T10:26:50.496Z
---

# Command::ERROR

# Description

ERROR constant to be used as command exit code

# Syntax

// src/Command/CreateUserCommand.php
namespace App\Command;

use Symfony\Component\Console\Command\Command;
use Symfony\Component\Console\Input\InputInterface;
use Symfony\Component\Console\Output\OutputInterface;

class CreateUserCommand extends Command
{
protected static \$defaultName = 'app:create-user';

```
// ...

protected function execute(InputInterface $input, OutputInterface $output)
{
    // ...

    // Before
    return 0;

    // After
    return Command::ERROR;
}
```

}

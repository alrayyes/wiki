---
publish: true
title: Console Cursor Control
created: 2020-11-16T13:41:42
modified: 2026-08-12T09:32:15.598Z
---

# Console Cursor Control

## Description

Allows cursor to be controlled

## Syntax

```php
namespace App\Command;

use Symfony\Component\Console\Command\Command;
use Symfony\Component\Console\Cursor;
use Symfony\Component\Console\Input\InputInterface;
use Symfony\Component\Console\Output\OutputInterface;

class SomeCommand extends Command
{
    protected static $defaultName = 'app:some-command';

    // ...

    protected function execute(InputInterface $input, OutputInterface $output)
    {
        // ...

        $cursor = new Cursor($output);

        // argument for left/right is "number of columns" (1 by default)
        // argument for top/bottom is "number of rows" (1 by default)
        $cursor->moveUp(2)->moveRight();
        $cursor->moveDown();

        // move to an arbitrary (column, row) position
        $cursor->moveToPosition(7, 15);

        // you can show/hide the cursor, save/restore its position, etc.
        $cursor->savePosition()->hide();
    }
}
```

```php
// clears the entire line where the cursor is at
$cursor->clearLine();

// clears the contents of the current line starting from the cursor position
$cursor->clearLineAfter();

// clears all the output from the cursors' current position to the end of the screen.
$cursor->clearOutput();

// clears the entire screen
$cursor->clearScreen();
```

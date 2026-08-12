---
publish: true
title: horizontalTable()
created: 2020-11-13T18:12:35
---

## Syntax

```php
use Symfony\Component\Console\Style\SymfonyStyle;

protected function execute(InputInterface $input, OutputInterface $output)
{
    $io = new SymfonyStyle($input, $output);
    $io->horizontalTable(
        ['ISBN', 'Title', 'Author'],
        [
            // ... the rows ...
        ]
    );
}
```

---
id: 5bae3aba-682a-4e09-b6b5-e71fabd8072d
title: horizontalTable()
---

# Syntax

``` php
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

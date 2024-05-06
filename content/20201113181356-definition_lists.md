---
id: e745d46a-809d-4c00-ada0-c2b99d1d4007
title: Definition Lists
---

# Syntax

``` php
use Symfony\Component\Console\Helper\TableSeparator;

$io->definitionList(
    ['Version' => '4.4.0'],
    ['Long-Term Support' => 'Yes'],
    new TableSeparator(),
    'Timeline',
    ['End of maintenance' => '11/2022'],
    ['End of life' => '11/2023']
);
```

# Output

``` shell
-------------------- ---------
Version 4.4.0
Long-Term Support Yes
-------------------- ---------
Timeline
End of maintenance 11/2022
End of life 11/2023
-------------------- ---------
```

---
id: f236ec20-fe58-437d-bfe1-a1ed58bcf3e0
title: Horizontal Tables
---

# Syntax

``` php
$table
    ->setHeaders(['ISBN', 'Title', 'Author'])
    ->setRows([
        // ... the rows ...
    ])
    ->setHorizontal()
;
```

# Output

``` shell
+--------+-----------------+----------------------+-----------------------+--------------------------+
| ISBN   | 99921-58-10-7   | 9971-5-0210-0        | 960-425-059-0         | 80-902734-1-6            |
| Title  | Divine Comedy   | A Tale of Two Cities | The Lord of the Rings | And Then There Were None |
| Author | Dante Alighieri | Charles Dickens      | J. R. R. Tolkien      | Agatha Christie          |
+--------+-----------------+----------------------+-----------------------+--------------------------+
```

---
publish: true
title: Horizontal Tables
created: 2020-11-13T18:09:28
modified: 2026-08-05T07:58:56.685Z
---

# Horizontal Tables

# Syntax

\$table
->setHeaders(\['ISBN', 'Title', 'Author'])
->setRows(\[
// ... the rows ...
])
->setHorizontal()
;

# Output

+--------+-----------------+----------------------+-----------------------+--------------------------+
| ISBN   | 99921-58-10-7   | 9971-5-0210-0        | 960-425-059-0         | 80-902734-1-6            |
| Title  | Divine Comedy   | A Tale of Two Cities | The Lord of the Rings | And Then There Were None |
| Author | Dante Alighieri | Charles Dickens      | J. R. R. Tolkien      | Agatha Christie          |
+--------+-----------------+----------------------+-----------------------+--------------------------+

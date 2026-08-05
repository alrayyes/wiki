---
publish: true
title: Definition Lists
created: 2020-11-13T18:13:56
modified: 2026-08-05T07:58:56.678Z
---

# Definition Lists

# Syntax

use Symfony\Component\Console\Helper\TableSeparator;

\$io->definitionList(
\['Version' => '4.4.0'],
\['Long-Term Support' => 'Yes'],
new TableSeparator(),
'Timeline',
\['End of maintenance' => '11/2022'],
\['End of life' => '11/2023']
);

# Output

---

Version 4.4.0
Long-Term Support Yes

---

Timeline
End of maintenance 11/2022
End of life 11/2023

---

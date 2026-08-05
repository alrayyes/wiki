---
publish: true
title: Symfony Console Hyperlinks
created: 2020-11-12T12:03:58
modified: 2026-08-05T10:26:50.517Z
---

# Symfony Console Hyperlinks

# Syntax

// hyperlink syntax: \<href=THE\_LINK\_URL> THE\_LINK\_TEXT \</>
$output->writeln('<href=https://symfony.com>Symfony Homepage</>');
$output->writeln('\<href=https://github.com/symfony/symfony/issues/29585>View Issue\</>');

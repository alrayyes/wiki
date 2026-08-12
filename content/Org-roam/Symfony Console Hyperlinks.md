---
publish: true
title: Symfony Console Hyperlinks
created: 2020-11-12T12:03:58
modified: 2026-08-12T10:31:55.434Z
---

# Symfony Console Hyperlinks

## Syntax

```php
// hyperlink syntax: <href=THE_LINK_URL> THE_LINK_TEXT </>
$output->writeln('<href=https://symfony.com>Symfony Homepage</>');
$output->writeln('<href=https://github.com/symfony/symfony/issues/29585>View Issue</>');
```

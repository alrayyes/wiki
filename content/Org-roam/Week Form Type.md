---
publish: true
title: Week Form Type
created: 2020-11-13T18:27:53
modified: 2026-08-12T09:32:15.645Z
---

# Week Form Type

## Description

\~WeekType~ form field that allows users to modify data that represents a specific ISO 8601[^iso] week number

## Syntax

```php
use Symfony\Component\Form\Extension\Core\Type\WeekType;

$builder->add('startDateTime', WeekType::class, [
    // use this if you store week numbers as strings ('2011-W17')
    'input' => 'string',
    // use this if you store week numbers as arrays (e.g. [2011, 17])
    'input' => 'array',

    // renders two <select> to select the year and week number
    'widget' => 'choice',
    // renders two <input type="text"> to write the year and week number
    'widget' => 'text',
    // renders a <input type="week"> which is properly rendered by most browsers
    'widget' => 'single_text',
]);
```

## Footnotes

[^iso]: https://en.wikipedia.org/wiki/ISO_week_date

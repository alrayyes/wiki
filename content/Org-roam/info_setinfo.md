---
publish: true
title: info() / setInfo()
created: 2020-11-16T14:30:04
modified: 2026-08-05T07:58:56.686Z
---

# info() / setInfo()

# Description

Add description/help/debug message to Resolver option

# Syntax

// using the traditional syntax
\$resolver->setInfo('scheduledAt', 'It must be a date in the future.');

// using the fluent interface
\$resolver->define('scheduledAt')
// ...
->info('It must be a date in the future.');

The option "scheduledAt" with value DateTime is invalid.
Info: It must be a date in the future.

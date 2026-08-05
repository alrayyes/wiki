---
publish: true
title: define()
created: 2020-11-16T14:27:09
modified: 2026-08-05T07:58:56.677Z
---

# define()

# Syntax

// Before
$resolver->setRequired('host');
$resolver->setDefaults(\['host' => 'smtp.example.org']);
\$resolver->setAllowedTypes('host', 'string');

// After
\$resolver->define('host')
->required()
->default('smtp.example.org')
->allowedTypes('string');

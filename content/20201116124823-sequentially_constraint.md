---
id: ee2c3e75-2f2a-44c0-b24d-b15ac3fd3bb6
title: Sequentially Constraint
---

# Description

Validates a set of constraints sequentially.

# Syntax

``` php
/**
 * @var string
 *
 * @Assert\Sequentially({
 *     @Assert\Type("string"),
 *     @Assert\Length(min="4"),
 *     @Assert\Regex("[a-z]"),
 *     @SomeCustomConstraintWithHeavyExternalCalls(),
 * })
 */
public $someProperty;
```

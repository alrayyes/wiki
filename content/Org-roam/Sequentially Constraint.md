---
publish: true
title: Sequentially Constraint
created: 2020-11-16T12:48:23
modified: 2026-08-12T10:31:55.429Z
---

# Sequentially Constraint

## Description

Validates a set of constraints sequentially.

## Syntax

```php
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

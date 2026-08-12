---
publish: true
title: Symfony Clear Form Errors
created: 2020-11-11T10:54:22
---

## Introduction

Introduced in [[Symfony 4.2]], ~clearErrors()~ allows us to remove any existing errors in forms. Some user cases:

- Partial form submissions with AJAX

## Syntax

```php
$task ={};
$form = $this->createForm(TaskType::class, $task);
// ...

$form->clearErrors();

// this removes errors from the form and all its children forms
$form->clearErrors(true);
```

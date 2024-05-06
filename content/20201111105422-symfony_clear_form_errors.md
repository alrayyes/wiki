---
id: 6e924661-5376-459d-9365-0054027c1755
title: Symfony Clear Form Errors
---

# Introduction

Introduced in [Symfony 4.2](20201111101706-symfony_4_2), `clearErrors()`
allows us to remove any existing errors in forms. Some user cases:

-   Partial form submissions with AJAX

# Syntax

``` php
$task ={};
$form = $this->createForm(TaskType::class, $task);
// ...

$form->clearErrors();

// this removes errors from the form and all its children forms
$form->clearErrors(true);
```

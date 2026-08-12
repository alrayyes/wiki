---
publish: true
title: Lazy Sessions
created: 2020-11-09T15:10:19
---

## Introduction

PHP 7.0 introduced a new interface called ~SessionUpdateTimestampHandlerInterface~. As of [[Symfony 4.0]] this has been added to the [[Symfony PHP7 Polyfill component]]

## Syntax

```php
interface SessionUpdateTimestampHandlerInterface
{
    // Checks if a session identifier already exists or not.
    public function validateId(string $key) : bool;

    // Updates the timestamp of a session when its data didn't change.
    public function updateTimestamp(string $key, string $val) : bool;
}
```

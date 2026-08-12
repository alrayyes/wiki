---
publish: true
title: Fallback For Internationalized Routes
created: 2020-11-11T11:16:36
---

# Fallback For Internationalized Routes

## Introduction

Since [[Symfony 4.2]], it's possible to define internationalized [[Fallback For Internationalized Routes]] without the region part. [[Symfony]] will match them ignoring the region part of the locacle.

## Syntax

```php
use Symfony\Component\Routing\Annotation\Route;

/**
 * @Route({ "en_GB": "/about-us", "en_US": "/about-us" }, name="about")
 */
public function about()
{
    // ...
}
```

can now be defined as

```php
/**
 * @Route({ "en": "/about-us" }, name="about")
 */
public function about()
{
    // ...
}
```

---
id: 2b3fbe1c-487f-40e0-88aa-a1b6d59093e3
title: Fallback For Internationalized Routes
---

# Introduction

Since [Symfony 4.2](20201111101706-symfony_4_2), it's possible to define
internationalized
[routes](20201111111636-fallback_for_internationalized_routes) without
the region part. [Symfony](20201109140300-symfony) will match them
ignoring the region part of the locacle.

# Syntax

``` php
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

``` php
/**
 * @Route({ "en": "/about-us" }, name="about")
 */
public function about()
{
    // ...
}
```

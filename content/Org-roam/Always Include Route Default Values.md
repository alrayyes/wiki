---
publish: true
title: Always Include Route Default Values
created: 2020-11-12T12:14:16
modified: 2026-08-12T09:32:15.592Z
---

# Always Include Route Default Values

## Description

Sometimes when generating URLs you have situations where you don't want the default value in the URL.

## Syntax

```php
/**
 * @Route("/blog/{!page}", name="blog_list")
 */
public function list($page = 1)
{
    // ...
}
```

```php
$url = $router->generate('blog_list');                // $url = '/blog/1'
$url = $router->generate('blog_list', ['page' => 1]); // $url = '/blog/1'
$url = $router->generate('blog_list', ['page' => 7]); // $url = '/blog/7'
```

```php
/**
 * @Route("/blog/{page}.{!_format<html|json>?html}", name="blog_list")
 */
public function list($page = 1)
{
    // ...
}
```

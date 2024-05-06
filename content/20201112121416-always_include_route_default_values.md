---
id: 63017411-62dd-4586-86c5-4b0edc70114d
title: Always Include Route Default Values
---

# Description

Sometimes when generating URLs you have situations where you don't want
the default value in the URL.

# Syntax

``` php
/**
 * @Route("/blog/{!page}", name="blog_list")
 */
public function list($page = 1)
{
    // ...
}
```

``` php
$url = $router->generate('blog_list');                // $url = '/blog/1'
$url = $router->generate('blog_list', ['page' => 1]); // $url = '/blog/1'
$url = $router->generate('blog_list', ['page' => 7]); // $url = '/blog/7'
```

``` php
/**
 * @Route("/blog/{page}.{!_format<html|json>?html}", name="blog_list")
 */
public function list($page = 1)
{
    // ...
}
```

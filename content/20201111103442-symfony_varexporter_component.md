---
id: a334a0bb-a462-4e8f-94df-6a9985a2c5e3
title: Symfony VarExporter Component
---

# Introduction

Introduced in [Symfony 4.2](20201111101706-symfony_4_2), the VarExporter
Component is a better alternative to PHP's `var_export()` function. The
`var_export()` function outputs or returns a parsable string
representation of a variable. It is similar to `var_dump()` with one
exception: the returned representation is valid PHP code. Symfony's
`export()` function is similar, but adds lots of useful features to it.

# Syntax

## Array

``` php
$data = array(123, array('abc'));
$result = VarExporter::export($data);
```

generates

``` php
<?php

return [
    123,
    [
        'abc',
    ],
];
```

## Class

``` php
class MySerializable implements \Serializable
{
    public function serialize()
    {
        return '123';
    }

    public function unserialize($data)
    {
        // do nothing
    }
}

$data = array(new MySerializable(), new MySerializable());
$result = VarExporter::export($data);
```

generates

``` php
<?php

return \Symfony\Component\VarExporter\Internal\Configurator::pop(
    \Symfony\Component\VarExporter\Internal\Registry::push([], [], [
        'C:50:"Symfony\\Component\\VarExporter\\Tests\\MySerializable":3:{123}',
    ]),
    null,
    [],
    [
        \Symfony\Component\VarExporter\Internal\Registry::$objects[0],
        \Symfony\Component\VarExporter\Internal\Registry::$objects[0],
    ],
    []
);
```

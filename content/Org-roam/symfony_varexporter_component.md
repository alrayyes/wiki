---
publish: true
title: Symfony VarExporter Component
created: 2020-11-11T10:34:42
modified: 2026-08-05T10:26:50.518Z
---

# Symfony VarExporter Component

# Introduction

Introduced in \[Symfony 4.2]\(Symfony 4.2), the VarExporter Component is a better alternative to PHP's ~var\_export()~ function. The ~var\_export()~ function outputs or returns a parsable string representation of a variable. It is similar to ~var\_dump()~ with one exception: the returned representation is valid PHP code. Symfony's ~export()~ function is similar, but adds lots of useful features to it.

# Syntax

## Array

$data = array(123, array('abc'));
$result = VarExporter::export(\$data);

generates

<?php

return [
    123,
    [
        'abc',
    ],
];
## Class
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

generates

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

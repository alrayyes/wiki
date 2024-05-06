---
id: e6d58583-98d8-4a0d-8d0b-a400ea4c2dc7
title: Expression Linter
---

# Description

Lint your expressions

# Syntax

``` php
use Symfony\Component\ExpressionLanguage\Lexer;
use Symfony\Component\ExpressionLanguage\Parser;

$lexer = new Lexer();
$parser = new Parser([]);
$parser->lint($lexer->tokenize($expression), $allowedVariableNames);

$expression = 'foo["some_key"].callFunction(a ? b)';
$allowedVariableNames = ['foo', 'a', 'b'];
// Result: no error; expression is valid.

$expression = 'foo["some_key")';
$allowedVariableNames = ['foo'];
// Result: Unclosed "[" around position 3 for expression `foo["some_key")`.

$expression = '{key: foo key2: bar}';
$allowedVariableNames = ['foo', 'bar'];
// Result: A hash value must be followed by a comma
//         Unexpected token "name" of value "key2" ("punctuation" expected with value ",")
//         around position 11 for expression `{key: foo key2: bar}`.
```

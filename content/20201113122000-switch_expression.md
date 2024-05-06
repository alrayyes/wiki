---
id: f9e3afdc-2d87-4ba2-a9de-758e403bff56
title: Switch expression
---

# Description

Probably a better idea to use [match](20201113121813-match_expression).

# Syntax

``` php
switch ($this->lexer->lookahead['type']) {
    case Lexer::T_SELECT:
        $statement = $this->SelectStatement();
        break;

    case Lexer::T_UPDATE:
        $statement = $this->UpdateStatement();
        break;

    case Lexer::T_DELETE:
        $statement = $this->DeleteStatement();
        break;

    default:
        $this->syntaxError('SELECT, UPDATE or DELETE');
        break;
}
```

---
publish: true
title: Switch expression
created: 2020-11-13T12:20:00
modified: 2026-08-05T07:58:56.711Z
---

# Switch expression

# Description

Probably a better idea to use \[Match expression]\(Match expression).

# Syntax

switch ($this->lexer->lookahead['type']) {
    case Lexer::T_SELECT:
        $statement = \$this->SelectStatement();
break;

```
case Lexer::T_UPDATE:
    $statement = $this->UpdateStatement();
    break;

case Lexer::T_DELETE:
    $statement = $this->DeleteStatement();
    break;

default:
    $this->syntaxError('SELECT, UPDATE or DELETE');
    break;
```

}

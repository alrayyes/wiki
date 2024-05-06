---
id: 0d9d39fc-149c-4190-a06d-1de455c930a4
title: Match expression
---

# Description

Match expressions[^1] are similar to
[switch](20201113122000-switch_expression), but with safer semantics and
the ability to return values.

# Syntax

``` php
// After
$statement = match ($this->lexer->lookahead['type']) {
    Lexer::T_SELECT => $this->SelectStatement(),
    Lexer::T_UPDATE => $this->UpdateStatement(),
    Lexer::T_DELETE => $this->DeleteStatement(),
    default => $this->syntaxError('SELECT, UPDATE or DELETE'),
};
```

## Return value

``` php
switch (1) {
    case 0:
        $result = 'Foo';
        break;
    case 1:
        $result = 'Bar';
        break;
    case 2:
        $result = 'Baz';
        break;
}

echo $result;
//> Bar

echo match (1) {
    0 => 'Foo',
    1 => 'Bar',
    2 => 'Baz',
};
//> Bar
```

## No type coercion

``` php
switch ('foo') {
    case 0:
      $result = "Oh no!\n";
      break;
    case 'foo':
      $result = "This is what I expected\n";
      break;
}
echo $result;
//> Oh no!

echo match ('foo') {
    0 => "Oh no!\n",
    'foo' => "This is what I expected\n",
};
//> This is what I expected
```

## No fallthrough

``` php
switch ($pressedKey) {
    case Key::RETURN_:
        save();
        // Oops, forgot the break
    case Key::DELETE:
        delete();
        break;
}

match ($pressedKey) {
    Key::RETURN_ => save(),
    Key::DELETE => delete(),
};

echo match ($x) {
    1, 2 => 'Same for 1 and 2',
    3, 4 => 'Same for 3 and 4',
};
```

## Exhaustiveness

``` php
switch ($operator) {
    case BinaryOperator::ADD:
        $result = $lhs + $rhs;
        break;
}

// Forgot to handle BinaryOperator::SUBTRACT

$result = match ($operator) {
    BinaryOperator::ADD => $lhs + $rhs,
};

// Throws when $operator is BinaryOperator::SUBTRACT
```

# Footnotes

[^1]: <https://wiki.php.net/rfc/match_expression_v2>

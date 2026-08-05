---
publish: true
title: Match expression
created: 2020-11-13T12:18:13
modified: 2026-08-05T10:26:50.509Z
---

# Match expression

# Description

Match expressions\[fn:rfc] are similar to \[Switch expression]\(Switch expression), but with safer semantics and the ability to return values.

# Syntax

// After
$statement = match ($this->lexer->lookahead\['type']) {
Lexer::T\_SELECT => $this->SelectStatement(),
    Lexer::T_UPDATE => $this->UpdateStatement(),
Lexer::T\_DELETE => $this->DeleteStatement(),
    default => $this->syntaxError('SELECT, UPDATE or DELETE'),
};

## Return value

switch (1) {
case 0:
$result = 'Foo';
        break;
    case 1:
        $result = 'Bar';
break;
case 2:
\$result = 'Baz';
break;
}

echo \$result;
//> Bar

echo match (1) {
0 => 'Foo',
1 => 'Bar',
2 => 'Baz',
};
//> Bar

## No type coercion

switch ('foo') {
case 0:
$result = "Oh no!\n";
      break;
    case 'foo':
      $result = "This is what I expected\n";
break;
}
echo \$result;
//> Oh no!

echo match ('foo') {
0 => "Oh no!\n",
'foo' => "This is what I expected\n",
};
//> This is what I expected

## No fallthrough

switch (\$pressedKey) {
case Key::RETURN\_:
save();
// Oops, forgot the break
case Key::DELETE:
delete();
break;
}

match (\$pressedKey) {
Key::RETURN\_ => save(),
Key::DELETE => delete(),
};

echo match (\$x) {
1, 2 => 'Same for 1 and 2',
3, 4 => 'Same for 3 and 4',
};

## Exhaustiveness

switch ($operator) {
    case BinaryOperator::ADD:
        $result = $lhs + $rhs;
break;
}

// Forgot to handle BinaryOperator::SUBTRACT

$result = match ($operator) {
BinaryOperator::ADD => $lhs + $rhs,
};

// Throws when \$operator is BinaryOperator::SUBTRACT

# Footnotes

\[fn:rfc]https://wiki.php.net/rfc/match\_expression\_v2

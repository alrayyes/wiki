---
publish: true
title: Type Constraint
created: 2020-11-13T17:25:17
modified: 2026-08-05T07:58:56.717Z
---

# Type Constraint

# Description

Validates that a given value is of a specific type. This type can be any of the valid PHP types\[fn:validtypes], any of the PHP ctype functions\[fn:ctypefunctions] (e.g. alnum, alpha, digit, etc.) and also the FQCN of any class

# Syntax

// src/Entity/Author.php
namespace App\Entity;

use Symfony\Component\Validator\Constraints as Assert;

class Author
{
/\*\*
\* @Assert\Type("Ramsey\Uuid\UuidInterface")
\*/
protected \$id;

```
/**
 * @Assert\Type("string")
 */
protected $firstName;

// ...
```

}

# Changelog

- \[Type Constraint Can Be An Array of Types]\(Type Constraint Can Be An Array of Types)

# Footnotes

\[fn:ctypefunctions]https://php.net/ref.ctype
\[fn:validtypes]https://www.php.net/manual/en/language.types.intro.php

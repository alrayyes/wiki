---
publish: true
title: NotBlank Constraint
created: 2020-11-12T13:07:10
modified: 2026-08-05T10:26:50.510Z
---

# NotBlank Constraint

# Syntax

namespace App\Entity;

use Symfony\Component\Validator\Constraints as Assert;

class SomeEntity
{
/\*\*
\* @Assert\NotBlank()
\*/
protected \$someProperty;
}

## allowNull

\[NotBlank allowNull]\(NotBlank allowNull)

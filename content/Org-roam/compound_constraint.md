---
publish: true
title: Compound Constraint
created: 2020-11-16T12:42:10
modified: 2026-08-05T07:58:56.675Z
---

# Compound Constraint

# Description

Use this when you want to use a set of \[Symfony Constraints]\(Symfony Constraints) in multiple places.

# Syntax

namespace App\Validator;

use Symfony\Component\Validator\Constraints\Compound;
use Symfony\Component\Validator\Constraints\Length;
use Symfony\Component\Validator\Constraints\NotBlank;
use Symfony\Component\Validator\Constraints\NotCompromisedPassword;
use Symfony\Component\Validator\Constraints\Type;

/\*\*

- @Annotation
  \*/
  class MatchesPasswordRequirements extends Compound
  {
  protected function getConstraints(array \$options): array
  {
  return \[
  new NotBlank(),
  new Type('string'),
  new Length(\['min' => 12]),
  new NotCompromisedPassword(),
  ];
  }
  }

namespace App\Dto;

// ...
use App\Validator\MatchesPasswordRequirements;

class ChangePasswordDto
{
/\*\*
\* @MatchesPasswordRequirements
\*/
private \$newPassword;

```
// ...
```

}

---
id: 6216c1c5-a482-4141-a5af-46917a1f8cd3
title: Compound Constraint
---

# Description

Use this when you want to use a set of
[constraints](20201112121938-symfony_constraints) in multiple places.

# Syntax

``` php
namespace App\Validator;

use Symfony\Component\Validator\Constraints\Compound;
use Symfony\Component\Validator\Constraints\Length;
use Symfony\Component\Validator\Constraints\NotBlank;
use Symfony\Component\Validator\Constraints\NotCompromisedPassword;
use Symfony\Component\Validator\Constraints\Type;

/**
 * @Annotation
 */
class MatchesPasswordRequirements extends Compound
{
    protected function getConstraints(array $options): array
    {
        return [
            new NotBlank(),
            new Type('string'),
            new Length(['min' => 12]),
            new NotCompromisedPassword(),
        ];
    }
}
```

``` php
namespace App\Dto;

// ...
use App\Validator\MatchesPasswordRequirements;

class ChangePasswordDto
{
    /**
     * @MatchesPasswordRequirements
     */
    private $newPassword;

    // ...
}
```

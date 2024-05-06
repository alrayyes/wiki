---
id: b632a78b-9e93-4b56-8cfe-daa3e4db12a2
title: Define Constraints as Attributes
---

# Syntax

## Annotations

``` php
// src/Entity/Author.php
namespace App\Entity;

// ...
use Symfony\Component\Validator\Constraints as Assert;

class Author
{
    /**
     * @Assert\Choice(
     *     choices = { "fiction", "non-fiction" },
     *     message = "Choose a valid genre."
     * )
     */
    private $genre;

    // ...
}
```

## Attributes

``` php
// src/Entity/Author.php
namespace App\Entity;

// ...
use Symfony\Component\Validator\Constraints as Assert;

class Author
{
    #[Assert\Choice(
        choices: ['fiction', 'non-fiction'],
        message: 'Choose a valid genre.',
    )]
    private $genre;

    // ...
}
```

# Caveats

The following composite constraints can't be used with attributes:

-   All
-   [AtLeastOneOf Constraint](20201116134435-atleastoneof_constraint)
-   Collection
-   [Compound Constraint](20201116124210-compound_constraint) (abstract)
    -   Existance (abstract)
        -   Required
        -   Optional
-   [Sequentially Constraint](20201116124823-sequentially_constraint)

The reason is that they would require nested attributes and PHP doesn’t
support that feature yet

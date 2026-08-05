---
publish: true
title: Define Constraints as Attributes
created: 2020-11-17T11:27:27
modified: 2026-08-05T10:26:50.498Z
---

# Define Constraints as Attributes

# Syntax

## Annotations

// src/Entity/Author.php
namespace App\Entity;

// ...
use Symfony\Component\Validator\Constraints as Assert;

class Author
{
/\*\*
\* @Assert\Choice(
\*     choices = { "fiction", "non-fiction" },
\*     message = "Choose a valid genre."
\* )
\*/
private \$genre;

```
// ...
```

}

## Attributes

// src/Entity/Author.php
namespace App\Entity;

// ...
use Symfony\Component\Validator\Constraints as Assert;

class Author
{
\#\[Assert\Choice(
choices: \['fiction', 'non-fiction'],
message: 'Choose a valid genre.',
)]
private \$genre;

```
// ...
```

}

# Caveats

The following composite constraints can't be used with attributes:

- All
- \[AtLeastOneOf Constraint]\(AtLeastOneOf Constraint)
- Collection
- \[Compound Constraint]\(Compound Constraint) (abstract)
  - Existance (abstract)
    - Required
    - Optional
- \[Sequentially Constraint]\(Sequentially Constraint)

The reason is that they would require nested attributes and PHP doesn’t support that feature yet

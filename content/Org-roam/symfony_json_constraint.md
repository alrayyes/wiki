---
publish: true
title: Symfony JSON Constraint
created: 2020-11-12T12:56:37
modified: 2026-08-05T10:26:50.517Z
---

# Symfony JSON Constraint

# Syntax

// src/Entity/Book.php
namespace App\Entity;

use Symfony\Component\Validator\Constraints as Assert;

class Book
{
/\*\*
\* @Assert\Json(message = "This is not valid JSON")
\*/
protected \$chapters;
}

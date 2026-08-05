---
publish: true
title: Automatic Validation Based on Doctrine Mapping
created: 2020-11-12T13:20:07
modified: 2026-08-05T10:26:50.494Z
---

# Automatic Validation Based on Doctrine Mapping

# Description

From \[Symfony 4.3]\(Symfony 4.3), Symfony introduces automatic validation based on Doctrine mapping.

# Examples

use Doctrine\ORM\Mapping as ORM;

/\*\* @ORM\Entity \*/
class SomeEntity
{
// ...

```
/** @ORM\Column(length=4) */
public $pinCode;
```

}

$entity = new SomeEntity();
$entity->pinCode = '1234567890';
$violationList = $validator->validate(\$entity);

$violationList = $validator->validate(\$entity);

var\_dump((string) \$violationList);
// Object(App\Entity\SomeEntity).columnLength:\n
//     This value is too long. It should have 4 characters or less.
//     (code d94b19cc-114f-4f44-9cc4-4138e80a87b9)\n

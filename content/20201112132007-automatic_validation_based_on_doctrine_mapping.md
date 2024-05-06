---
id: c7132269-2084-4d87-9888-0f860db29aaf
title: Automatic Validation Based on Doctrine Mapping
---

# Description

From [Symfony 4.3](20201112120118-symfony_4_3), Symfony introduces
automatic validation based on Doctrine mapping.

# Examples

``` php
use Doctrine\ORM\Mapping as ORM;

/** @ORM\Entity */
class SomeEntity
{
    // ...

    /** @ORM\Column(length=4) */
    public $pinCode;
}
```

``` php
$entity = new SomeEntity();
$entity->pinCode = '1234567890';
$violationList = $validator->validate($entity);
```

``` php
$violationList = $validator->validate($entity);

var_dump((string) $violationList);
// Object(App\Entity\SomeEntity).columnLength:\n
//     This value is too long. It should have 4 characters or less.
//     (code d94b19cc-114f-4f44-9cc4-4138e80a87b9)\n
```

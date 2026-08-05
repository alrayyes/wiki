---
publish: true
title: Validate BIC and IBAN Codes Together
created: 2020-11-12T12:32:44
modified: 2026-08-05T07:58:56.721Z
---

# Validate BIC and IBAN Codes Together

# Syntax

use Symfony\Component\Validator\Constraints as Assert;
// ...

public static function loadValidatorMetadata(ClassMetadata $metadata)
{
    $metadata->addPropertyConstraint('businessIdentifierCode', new Assert\Bic(\[
'iban' => 'FR1420041010050500013M02606',
]));
}

use Symfony\Component\Validator\Constraints as Assert;
// ...

class Transaction
{
/\*\*
\* @Assert\Bic(ibanPropertyPath = "accountNumber")
\*/
protected \$businessIdentifierCode;

```
/**
 * @Assert\Iban
 */
protected $accountNumber;

// public getters for properties ...
```

}

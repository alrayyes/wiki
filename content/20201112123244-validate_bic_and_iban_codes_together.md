---
id: 65f016de-b501-447f-bf81-6bf4f196330f
title: Validate BIC and IBAN Codes Together
---

# Syntax

``` php
use Symfony\Component\Validator\Constraints as Assert;
// ...

public static function loadValidatorMetadata(ClassMetadata $metadata)
{
    $metadata->addPropertyConstraint('businessIdentifierCode', new Assert\Bic([
        'iban' => 'FR1420041010050500013M02606',
    ]));
}
```

``` php
use Symfony\Component\Validator\Constraints as Assert;
// ...

class Transaction
{
    /**
     * @Assert\Bic(ibanPropertyPath = "accountNumber")
     */
    protected $businessIdentifierCode;

    /**
     * @Assert\Iban
     */
    protected $accountNumber;

    // public getters for properties ...
}
```

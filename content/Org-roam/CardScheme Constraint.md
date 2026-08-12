---
publish: true
title: CardScheme Constraint
created: 2020-11-12T12:37:04
---

See Universal Air Travel Plan[^uatp] for more details.

## Syntax

```php
// ...

class Transaction
{
    /**
     * @Assert\CardScheme(
     *     schemes={"AMEX", "MASTERCARD", "UATP", "VISA"},
     *     message="Your credit card number is invalid."
     * )
     */
    protected $cardNumber;
}
```

## Footnotes

[^uatp]: https://en.wikipedia.org/wiki/Universal_Air_Travel_Plan

---
publish: true
title: CardScheme Constraint
created: 2020-11-12T12:37:04
modified: 2026-08-12T10:26:13.160Z
---

# CardScheme Constraint

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

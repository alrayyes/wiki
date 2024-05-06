---
id: c74d4f32-ff6b-419e-8ed7-eb0b018de44d
title: CardScheme Constraint
---

See Universal Air Travel Plan[^1] for more details.

# Syntax

``` php
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

# Footnotes

[^1]: <https://en.wikipedia.org/wiki/Universal_Air_Travel_Plan>

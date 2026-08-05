---
publish: true
title: CardScheme Constraint
created: 2020-11-12T12:37:04
modified: 2026-08-05T10:26:50.495Z
---

# CardScheme Constraint

See Universal Air Travel Plan\[fn:uatp] for more details.

# Syntax

// ...

class Transaction
{
/\*\*
\* @Assert\CardScheme(
\*     schemes={"AMEX", "MASTERCARD", "UATP", "VISA"},
\*     message="Your credit card number is invalid."
\* )
\*/
protected \$cardNumber;
}

# Footnotes

\[fn:uatp]https://en.wikipedia.org/wiki/Universal\_Air\_Travel\_Plan

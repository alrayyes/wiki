---
publish: true
title: ExpressionLanguageSyntax Constraint
created: 2020-11-16T13:55:23
modified: 2026-08-05T10:26:50.501Z
---

# ExpressionLanguageSyntax Constraint

# Description

Checks that passed \[ExpressionLanguage Constraint]\(ExpressionLanguage Constraint) is valid.

# Syntax

namespace App\Entity;

use Symfony\Component\Validator\Constraints as Assert;

class Order
{
/\*\*
\* @Assert\ExpressionLanguageSyntax()
\*/
protected \$promotion;

```
/**
 * @Assert\ExpressionLanguageSyntax(
 *     names = ['user', 'shipping_centers'],
 *     validateNames = true
 * )
 */
protected $shippingOptions;
```

}

---
id: 4e2ed7c3-2dba-46f7-922c-2b02bf7bcfbd
title: AtLeastOneOf Constraint
---

# Description

At least one of the given constraints must be satisfied

# Syntax

``` php
namespace App\Entity;

use Symfony\Component\Validator\Constraints as Assert;

class SomeEntity
{
    /**
     * @Assert\AtLeastOneOf({
     *     @Assert\Length(min=5),
     *     @Assert\EqualTo("bar")
     * })
     */
    public $name = 'foo';

    /**
     * @Assert\AtLeastOneOf({
     *     @Assert\All({@Assert\GreaterThanOrEqual(10)}),
     *     @Assert\Count(20)
     * })
     */
    public $numbers = ['3', '5'];

    /**
     * @Assert\All({
     *     @Assert\AtLeastOneOf({
     *          @Assert\GreaterThanOrEqual(5),
     *          @Assert\LessThanOrEqual(3)
     *     })
     * })
     */
    public $otherNumbers = ['4', '5'];
}
```

By default, the error messages lists all the failed conditions:

    name: This value should satisfy at least one of the following constraints:
    [1] This value is too short. It should have 5 characters or more.
    [2] This value should be equal to "bar".

    numbers: This value should satisfy at least one of the following constraints:
    [1] Each element of this collection should satisfy its own set of constraints.
    [2] This collection should contain exactly 20 elements.

    otherNumbers[0]: This value should satisfy at least one of the following constraints:
    [1] This value should be greater than or equal to 5.
    [2] This value should be less than or equal to 3.

---
id: f028709b-5851-4a8e-8c3c-097ebbe27c39
title: Timezozne Constraint
---

# Syntax

``` php
// src/Entity/UserSettings.php
namespace App\Entity;

use Symfony\Component\Validator\Constraints as Assert;

class UserSettings
{
    /**
     * @Assert\Timezone
     */
    protected $timezone;
}
```

``` php
// Consider valid only the timezones from countries in America continent

/** @Assert\Timezone(zone=\DateTimeZone::AMERICA) */
protected $timezone;

// Consider valid only the Chinese timezones

/** @Assert\Timezone(zone=\DateTimeZone::PER_COUNTRY, countryCode="CN") */
protected $timezone;
```

# Related

-   [Symfony Constraints](20201112121938-symfony_constraints)
-   [Symfony Annotations](20201109142218-symfony_annotations)
-   [Symfony 4.3](20201112120118-symfony_4_3)

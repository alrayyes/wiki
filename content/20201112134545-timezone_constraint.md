---
id: ba952b1d-0609-4bc6-94b9-0192df3bf4f2
title: Timezone Constraint
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

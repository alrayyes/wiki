---
publish: true
title: Timezone Constraint
created: 2020-11-12T13:45:45
---

# Timezone Constraint

## Syntax

```php
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

```php
// Consider valid only the timezones from countries in America continent

/** @Assert\Timezone(zone=\DateTimeZone::AMERICA) */
protected $timezone;

// Consider valid only the Chinese timezones

/** @Assert\Timezone(zone=\DateTimeZone::PER_COUNTRY, countryCode="CN") */
protected $timezone;
```

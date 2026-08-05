---
publish: true
title: Timezone Constraint
created: 2020-11-12T13:45:45
modified: 2026-08-05T07:58:56.716Z
---

# Timezone Constraint

# Syntax

// src/Entity/UserSettings.php
namespace App\Entity;

use Symfony\Component\Validator\Constraints as Assert;

class UserSettings
{
/\*\*
\* @Assert\Timezone
\*/
protected \$timezone;
}

// Consider valid only the timezones from countries in America continent

/\*\* @Assert\Timezone(zone=\DateTimeZone::AMERICA) \*/
protected \$timezone;

// Consider valid only the Chinese timezones

/\*\* @Assert\Timezone(zone=\DateTimeZone::PER\_COUNTRY, countryCode="CN") \*/
protected \$timezone;

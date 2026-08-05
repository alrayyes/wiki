---
publish: true
title: Timezozne Constraint
created: 2020-11-12T13:45:45
modified: 2026-08-05T10:26:50.519Z
---

# Timezozne Constraint

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

# Related

- \[Symfony Constraints]\(Symfony Constraints)
- \[Symfony Annotations]\(Symfony Annotations)
- \[Symfony 4.3]\(Symfony 4.3)

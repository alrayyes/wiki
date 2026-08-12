---
publish: true
title: Password Migrations
created: 2020-11-13T18:17:59
modified: 2026-08-12T10:26:13.191Z
---

# Password Migrations

## Description

Automatically upgrade password hashes by using ~PasswordUpgraderInterface~ interface

## Syntax

```yaml
# config/packages/security.yaml
security:
    # ...
    encoders:
        App\Entity\User:
            algorithm: 'argon2i'
            migrate_from: 'bcrypt'
```

```php
// src/Repository/UserRepository.php
namespace App\Repository;

// ...
use Symfony\Component\Security\Core\User\PasswordUpgraderInterface;

class UserRepository extends EntityRepository implements PasswordUpgraderInterface
{
    // ...

    public function upgradePassword(UserInterface $user, string $newEncodedPassword): void
    {
        // this code is only an example; the exact code will depend on
        // your own application needs
        $user->setPassword($newEncodedPassword);
        $this->getEntityManager()->flush($user);
    }
}
```

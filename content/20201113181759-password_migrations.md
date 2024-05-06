---
id: 11f17415-46cc-4100-ab3d-4e552dd8886e
title: Password Migrations
---

# Description

Automatically upgrade password hashes by using
`PasswordUpgraderInterface` interface

# Syntax

``` yaml
# config/packages/security.yaml
security:
    # ...
    encoders:
        App\Entity\User:
            algorithm: 'argon2i'
            migrate_from: 'bcrypt'
```

``` php
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

---
publish: true
title: CurrentUser
created: 2020-11-17T10:27:46
modified: 2026-08-05T10:26:50.497Z
---

# CurrentUser

# Description

Turns controller argument into the object that represents the currently logged in user.

# Syntax

// src/Controller/SomeController.php
namespace App\Controller;

use App\Entity\MyUser;
use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\Security\Http\Attribute\CurrentUser;

class SomeController extends AbstractController
{
public function index(#\[CurrentUser] MyUser \$user)
{
// ...
}
}

---
publish: true
title: Fallback For Internationalized Routes
created: 2020-11-11T11:16:36
modified: 2026-08-05T10:26:50.501Z
---

# Fallback For Internationalized Routes

# Introduction

Since \[Symfony 4.2]\(Symfony 4.2), it's possible to define internationalized \[Fallback For Internationalized Routes]\(Fallback For Internationalized Routes) without the region part. [Symfony](Symfony) will match them ignoring the region part of the locacle.

# Syntax

use Symfony\Component\Routing\Annotation\Route;

/\*\*

- @Route({ "en\_GB": "/about-us", "en\_US": "/about-us" }, name="about")
  \*/
  public function about()
  {
  // ...
  }

can now be defined as

/\*\*

- @Route({ "en": "/about-us" }, name="about")
  \*/
  public function about()
  {
  // ...
  }

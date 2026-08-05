---
publish: true
title: Simpler Event Listeners
created: 2020-11-13T18:02:27
modified: 2026-08-05T07:58:56.709Z
---

# Simpler Event Listeners

# Syntax

# config/services.yaml

services:
App\EventListener\MyRequestListener:
tags:
\- { name: kernel.event\_listener }

namespace App\EventListener;

use Symfony\Component\HttpKernel\Event\RequestEvent;

final class MyRequestListener
{
public function \_\_invoke(RequestEvent \$event): void
{
// ...
}
}

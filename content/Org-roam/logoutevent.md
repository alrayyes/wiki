---
publish: true
title: LogoutEvent
created: 2020-11-16T13:39:07
modified: 2026-08-05T10:26:50.509Z
---

# LogoutEvent

# Description

Replaces ~LogoutSuccessHandlerInterface~ and ~LogougHandlerInterface~

# Syntax

# config/services.yaml

services:
\# ...
App\EventListener\MyCutomLogoutListener:
tags:
\- name: 'kernel.event\_listener'
event: 'Symfony\Component\Security\Http\Event\LogoutEvent'
dispatcher: security.event\_dispatcher.main

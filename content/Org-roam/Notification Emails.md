---
publish: true
title: Notification Emails
created: 2020-11-13T17:40:16
modified: 2026-08-12T10:31:55.419Z
---

# Notification Emails

## Description

Standardized messages used to send notifications to yourself

## Syntax

```php
use Symfony\Bridge\Twig\Mime\NotificationEmail;

$email = (new NotificationEmail())
    ->from('fabien@example.com')
    ->to('fabien@example.org')
    ->subject('My first notification email via Symfony')
    ->markdown(<<<EOF
        There is a **problem** on your website, you should investigate it
        right now. Or just wait, the problem might solves itself automatically,
        we never know.
        EOF
    )
    ->action('More info?', 'https://example.com/')
    ->importance(NotificationEmail::IMPORTANCE_HIGH)
;
```

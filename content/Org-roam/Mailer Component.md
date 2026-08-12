---
publish: true
title: Mailer Component
created: 2020-11-12T13:52:49
modified: 2026-08-12T09:32:15.623Z
---

# Mailer Component

## Description

Added in [[Symfony 4.3]]. Out of the box the following services are supported:

- Amazon SES
- MailChimp
- Mailgun
- Gmail
- Postmark
- SendGrid

Services need to be installed seperately:

```shell
composer require symfony/amazon-mailer
```

And environment variables need to be configured:

```shell
AWS_ACCESS_KEY=...
AWS_SECRET_KEY=...
MAILER_DSN=smtp://$AWS_ACCESS_KEY:$AWS_SECRET_KEY@ses
```

## Syntax

```php
use Symfony\Component\Mailer\MailerInterface;
use Symfony\Component\Mime\Email;

class SomeService
{
    private $mailer;

    public function __construct(MailerInterface $mailer)
    {
        $this->mailer = $mailer;
    }

    public function sendNotification()
    {
        $email = (new Email())
            ->from('hello@example.com')
            ->to('you@example.com')
            ->subject('Time for Symfony Mailer!')
            ->text('Sending emails is fun again!')
            ->html('<p>See Twig integration for better HTML integration!</p>');

        $this->mailer->send($email);
    }
}
```

## Signing Messages

It's also possible to [[Signing and Encrypting Messages]] messages.

## DKIM email authentication

- DKIM[^dkim] authentication is [[DKIM Email Authentication]] as well.

## Footnotes

[^dkim]: https://en.wikipedia.org/wiki/DomainKeys_Identified_Mail

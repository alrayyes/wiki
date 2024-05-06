---
id: c6a317d3-cdda-4c9b-bf03-5e36bce8bc57
title: Mailer Component
---

# Description

Added in [Symfony 4.3](20201112120118-symfony_4_3). Out of the box the
following services are supported:

-   Amazon SES
-   MailChimp
-   Mailgun
-   Gmail
-   Postmark
-   SendGrid

Services need to be installed seperately:

``` shell
composer require symfony/amazon-mailer
```

And environment variables need to be configured:

``` shell
AWS_ACCESS_KEY=...
AWS_SECRET_KEY=...
MAILER_DSN=smtp://$AWS_ACCESS_KEY:$AWS_SECRET_KEY@ses
```

# Syntax

``` php
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

# Signing Messages

It's also possible to [sign and
encrypt](20201113173159-signing_and_encrypting_messages) messages.

# DKIM email authentication

-   DKIM[^1] authentication is
    [supported](20201117104659-dkim_email_authentication) as well.

# Footnotes

[^1]: <https://en.wikipedia.org/wiki/DomainKeys_Identified_Mail>

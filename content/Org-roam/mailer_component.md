---
publish: true
title: Mailer Component
created: 2020-11-12T13:52:49
modified: 2026-08-05T10:26:50.509Z
---

# Mailer Component

# Description

Added in \[Symfony 4.3]\(Symfony 4.3). Out of the box the following services are supported:

- Amazon SES
- MailChimp
- Mailgun
- Gmail
- Postmark
- SendGrid

Services need to be installed seperately:

composer require symfony/amazon-mailer

And environment variables need to be configured:

AWS\_ACCESS\_KEY=...
AWS\_SECRET\_KEY=...
MAILER\_DSN=smtp://$AWS_ACCESS_KEY:$AWS\_SECRET\_KEY@ses

# Syntax

use Symfony\Component\Mailer\MailerInterface;
use Symfony\Component\Mime\Email;

class SomeService
{
private \$mailer;

```
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
```

}

# Signing Messages

It's also possible to \[Signing and Encrypting Messages]\(Signing and Encrypting Messages) messages.

# DKIM email authentication

- DKIM\[fn:dkim] authentication is \[DKIM Email Authentication]\(DKIM Email Authentication) as well.

# Footnotes

\[fn:dkim]https://en.wikipedia.org/wiki/DomainKeys\_Identified\_Mail

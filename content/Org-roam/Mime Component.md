---
publish: true
title: Mime Component
created: 2020-11-12T14:06:50
modified: 2026-08-12T09:44:58.341Z
---

# Mime Component

## Syntax

```php
use Symfony\Component\Mime\Email;

$email = (new Email())
    ->from('fabien@symfony.com')
    ->to('foo@example.com')
    ->subject('Important Notification')
    ->text('Lorem ipsum...')
    ->html('<h1>Lorem ipsum</h1> <p>...</p>')
;
```

```php
use Symfony\Component\Mime\Header\Headers;
use Symfony\Component\Mime\Message;
use Symfony\Component\Mime\Part\Multipart\AlternativePart;
use Symfony\Component\Mime\Part\TextPart;

$headers = (new Headers())
    ->addMailboxListHeader('From', ['fabien@symfony.com'])
    ->addMailboxListHeader('To', ['foo@example.com'])
    ->addTextHeader('Subject', 'Important Notification')
;

$textContent = new TextPart('Lorem ipsum...');
$htmlContent = new TextPart('<h1>Lorem ipsum</h1> <p>...</p>', 'html');
$body = new AlternativePart($textContent, $htmlContent);

$email = new Message($headers, $body);
```

### Twig integeration

```php
use Symfony\Bridge\Twig\Mime\TemplatedEmail;

$email = (new TemplatedEmail())
    ->from('fabien@symfony.com')
    ->to('foo@example.com')
    // ...

    // this method defines the path of the Twig template to render
    ->htmlTemplate('messages/user/signup.html.twig')

    // this method defines the parameters (name => value) passed to templates
    ->context([
        'expiration_date' => new \DateTime('+7 days'),
        'username' => 'foo',
    ])
;
```

## Changelog

- [[Notification Emails]]

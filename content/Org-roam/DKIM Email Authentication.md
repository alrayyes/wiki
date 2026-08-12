---
publish: true
title: DKIM Email Authentication
created: 2020-11-17T10:46:59
modified: 2026-08-12T09:32:15.601Z
---

# DKIM Email Authentication

## Description

DKIM[^dkim] is supported by the [[Mailer Component]]. There is also documentation[^docs].

## Syntax

```php
use Symfony\Component\Mime\Crypto\DkimSigner;
use Symfony\Component\Mime\Email;

$email = (new Email())
    ->from('hello@example.com')
    // ...
    ->html('...');

$signer = new DkimSigner('file:///path/to/private-key.key', 'example.com', 'sf');
$signedEmail = $signer->sign($email);
```

## Footnotes

[^docs]: https://symfony.com/doc/master/mailer.html#dkim-signer

[^dkim]: https://en.wikipedia.org/wiki/DomainKeys_Identified_Mail

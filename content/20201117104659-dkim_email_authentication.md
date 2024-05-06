---
id: fd4d659f-01f1-4246-87ec-b8073a363402
title: DKIM Email Authentication
---

# Description

DKIM[^1] is supported by the [Mailer
Component](20201112135249-mailer_component). There is also
documentation[^2].

# Syntax

``` php
use Symfony\Component\Mime\Crypto\DkimSigner;
use Symfony\Component\Mime\Email;

$email = (new Email())
    ->from('hello@example.com')
    // ...
    ->html('...');

$signer = new DkimSigner('file:///path/to/private-key.key', 'example.com', 'sf');
$signedEmail = $signer->sign($email);
```

# Footnotes

[^1]: <https://en.wikipedia.org/wiki/DomainKeys_Identified_Mail>

[^2]: <https://symfony.com/doc/master/mailer.html#dkim-signer>

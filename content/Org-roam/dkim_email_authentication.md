---
publish: true
title: DKIM Email Authentication
created: 2020-11-17T10:46:59
modified: 2026-08-05T10:26:50.499Z
---

# DKIM Email Authentication

# Description

DKIM\[fn:dkim] is supported by the \[Mailer Component]\(Mailer Component). There is also documentation\[fn:docs].

# Syntax

use Symfony\Component\Mime\Crypto\DkimSigner;
use Symfony\Component\Mime\Email;

\$email = (new Email())
->from('hello@example.com')
// ...
->html('...');

$signer = new DkimSigner('file:///path/to/private-key.key', 'example.com', 'sf');
$signedEmail = $signer->sign($email);

# Footnotes

\[fn:docs]https://symfony.com/doc/master/mailer.html#dkim-signer

\[fn:dkim]https://en.wikipedia.org/wiki/DomainKeys\_Identified\_Mail

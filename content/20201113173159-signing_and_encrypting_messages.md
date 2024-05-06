---
id: 9256ee27-61e2-4c9f-b49c-bc2efe01d528
title: Signing and Encrypting Messages
---

# Description

Emails can be signed an encrypted using the S/MIME[^1] standard.

# Syntax

## Signing

``` php
use Symfony\Component\Mime\Crypto\SMimeSigner;
use Symfony\Component\Mime\Email;

$email = (new Email())->from('...')->to('...')->html('...');

$signer = new SMimeSigner('/path/to/certificate.crt', '/path/to/certificate-private-key.key');
$signedEmail = $signer->sign($email);
// now use the Mailer to send this $signedEmail instead of the original $email

```

## Encrypting

``` php
use Symfony\Component\Mime\Crypto\SMimeEncrypter;
use Symfony\Component\Mime\Email;

$email = (new Email())->from('...')->to('...')->html('...');

$encrypter = new SMimeEncrypter('/path/to/certificate.crt');
$encryptedEmail = $encrypter->encrypt($email);
// now use the Mailer to send this $encryptedEmail instead of the original $email
```

# Footnotes

[^1]: <https://en.wikipedia.org/wiki/S/MIME>

---
publish: true
title: Signing and Encrypting Messages
created: 2020-11-13T17:31:59
modified: 2026-08-05T07:58:56.709Z
---

# Signing and Encrypting Messages

# Description

Emails can be signed an encrypted using the S/MIME\[fn:mime] standard.

# Syntax

## Signing

use Symfony\Component\Mime\Crypto\SMimeSigner;
use Symfony\Component\Mime\Email;

\$email = (new Email())->from('...')->to('...')->html('...');

$signer = new SMimeSigner('/path/to/certificate.crt', '/path/to/certificate-private-key.key');
$signedEmail = $signer->sign($email);
// now use the Mailer to send this $signedEmail instead of the original $email

## Encrypting

use Symfony\Component\Mime\Crypto\SMimeEncrypter;
use Symfony\Component\Mime\Email;

\$email = (new Email())->from('...')->to('...')->html('...');

$encrypter = new SMimeEncrypter('/path/to/certificate.crt');
$encryptedEmail = $encrypter->encrypt($email);
// now use the Mailer to send this $encryptedEmail instead of the original $email

# Footnotes

\[fn:mime]https://en.wikipedia.org/wiki/S/MIME

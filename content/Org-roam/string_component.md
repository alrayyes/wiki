---
publish: true
title: String Component
created: 2020-11-13T18:34:42
modified: 2026-08-05T10:26:50.516Z
---

# String Component

# Syntax

## Working with strings

use Symfony\Component\String\ByteString;
use Symfony\Component\String\CodePointString;
use Symfony\Component\String\UnicodeString;

$content = new CodePointString('Hello world');
$content = new UnicodeString('नमस्ते दुनिया');
\$content = new ByteString('さよなら');

$content = (new CodePointString('hello'))->toUnicodeString();
$content = UnicodeString::fromCodePoints(0x68, 0x65, 0x6C, 0x6C, 0x6F)->toByteString();

use function Symfony\Component\String\b;
use function Symfony\Component\String\u;

// both are equivalent
$content = b('hello');
$content = new ByteString('hello');

// both are equivalent
$content = u('hello');
$content = new UnicodeString('hello');

## Object-oriented strings

// using PHP functions
if ('.html' === substr(\$theString, -strlen('.html'))) {
// ...
}

// using Symfony's String
if (u(\$theString)->endsWith('.html')) {
// ...
}

$text =u('This is a déjà-vu situation.')
    ->trimEnd('.')
    ->replace('déjà-vu', 'jamais-vu')
    ->append('!');
// $text = 'This is a jamais-vu situation!'

u('FOO Bar')->folded();             // 'foo bar'
u('Die O'Brian Straße')->folded(); // "die o'brian strasse"

## String Slugger

use Symfony\Component\String\Slugger\AsciiSlugger;

$slugger = new AsciiSlugger();
$slugger->slug('Стойността трябва', '-', 'bg');  // 'Stoinostta-tryabva'
$slugger->slug('Αυτή η τιμή πρέπει', '-', 'el'); // 'Avti-i-timi-prepi'
$slugger->slug('该变量的值应为', '-', 'zh');       // 'gai-bian-liang-de-zhi-ying-wei'
\$slugger->slug('Wôrķšƥáçè sèťtïñğš');            // 'Workspace-settings'

## Twig Integration

{{ 'Lorem ipsum'|u.truncate(8, '...') }}
{# prints: Lorem... #}

{{ 'SymfonyStringWithTwig'|u.snake }}
{# prints: symfony\_string\_with\_twig #}

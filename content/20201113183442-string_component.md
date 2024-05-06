---
id: 36b7429a-aeba-45bf-beaa-98add87e1504
title: String Component
---

# Syntax

## Working with strings

``` php
use Symfony\Component\String\ByteString;
use Symfony\Component\String\CodePointString;
use Symfony\Component\String\UnicodeString;

$content = new CodePointString('Hello world');
$content = new UnicodeString('नमस्ते दुनिया');
$content = new ByteString('さよなら');

$content = (new CodePointString('hello'))->toUnicodeString();
$content = UnicodeString::fromCodePoints(0x68, 0x65, 0x6C, 0x6C, 0x6F)->toByteString();
```

``` php
use function Symfony\Component\String\b;
use function Symfony\Component\String\u;

// both are equivalent
$content = b('hello');
$content = new ByteString('hello');

// both are equivalent
$content = u('hello');
$content = new UnicodeString('hello');
```

## Object-oriented strings

``` php
// using PHP functions
if ('.html' === substr($theString, -strlen('.html'))) {
    // ...
}

// using Symfony's String
if (u($theString)->endsWith('.html')) {
    // ...
}
```

``` php
$text =u('This is a déjà-vu situation.')
    ->trimEnd('.')
    ->replace('déjà-vu', 'jamais-vu')
    ->append('!');
// $text = 'This is a jamais-vu situation!'
```

``` php
u('FOO Bar')->folded();             // 'foo bar'
u('Die O\'Brian Straße')->folded(); // "die o'brian strasse"
```

## String Slugger

``` php
use Symfony\Component\String\Slugger\AsciiSlugger;

$slugger = new AsciiSlugger();
$slugger->slug('Стойността трябва', '-', 'bg');  // 'Stoinostta-tryabva'
$slugger->slug('Αυτή η τιμή πρέπει', '-', 'el'); // 'Avti-i-timi-prepi'
$slugger->slug('该变量的值应为', '-', 'zh');       // 'gai-bian-liang-de-zhi-ying-wei'
$slugger->slug('Wôrķšƥáçè sèťtïñğš');            // 'Workspace-settings'
```

## Twig Integration

``` twig
{{ 'Lorem ipsum'|u.truncate(8, '...') }}
{# prints: Lorem... #}

{{ 'SymfonyStringWithTwig'|u.snake }}
{# prints: symfony_string_with_twig #}
```

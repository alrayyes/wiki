---
id: ec38d6f0-c958-478b-9701-99a535b9adc9
title: Symfony String Component
---

# Interfaces

-   [Stringable Interface](20201116125716-stringable_interface)

# Syntax

-   [containsAny()](20201116130503-containsany)
-   [fromRandom()](20201116142317-fromrandom)
-   [reverse()](20201116130738-reverse)
-   [truncate()](20201116130210-truncate)

## Misc

### String conversion

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

### Object-oriented strings

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

### String Slugger

``` php
use Symfony\Component\String\Slugger\AsciiSlugger;

$slugger = new AsciiSlugger();
$slugger->slug('Стойността трябва', '-', 'bg');  // 'Stoinostta-tryabva'
$slugger->slug('Αυτή η τιμή πρέπει', '-', 'el'); // 'Avti-i-timi-prepi'
$slugger->slug('该变量的值应为', '-', 'zh');       // 'gai-bian-liang-de-zhi-ying-wei'
$slugger->slug('Wôrķšƥáçè sèťtïñğš');            // 'Workspace-settings'
```

### Twig Integration

``` twig
{{ 'Lorem ipsum'|u.truncate(8, '...') }}
{# prints: Lorem... #}

{{ 'SymfonyStringWithTwig'|u.snake }}
{# prints: symfony_string_with_twig #}
```

# Related

-   [Symfony Components](20201110152627-symfony_components)
-   [Symfony 5.0](20201113172025-symfony_5_0)

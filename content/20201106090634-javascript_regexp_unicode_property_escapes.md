---
id: 5441479c-12e5-48c1-ab17-46a9c3df8bc3
title: JavaScript RegExp Unicode Property Escapes
---

# Description

Characters can be matched by mentioning their Unicode character
properties inside of `\p{}`:

# Proposal

RegExp Unicode Property Escapes[^1]

# Syntax

``` javascript
console.log(/^\p{White_Space}+$/u.test("\t \n\r")); // true
console.log(/^\p{Script=Greek}+$/u.test("μετά")); // true
```

# Properties

## Examples

### Name

A unique name, composed of uppercase letters, digits, hyphens and
spaces.

-   A: Name = LATIN CAPITAL LETTER A
-   🙂: Name = SLIGHTLY SMILING FACE

### General~Category~

categorizes characters

-   x: General~Category~ = Lowercase~Letter~
-   \$: General~Category~ = Currency~Symbol~

### White~Scpace~

Used for marking invisible spacing characters, such as spaces, tabs and
newlines.

-   :͡ White~Space~ = True
-   π: White~Space~ = False

### Age

Version of the Unicode Standard in which a character was introduced. For
example: The Euro sign € was added in version 2.1 of the Unicode
standard.

-   €: Age = 2.1

### Block

A contiguous range of code points. Blocks don’t overlap and their names
are unique.

-   S: Block = Basic~Latin~ (range U+0000..U+007F)
-   🙂: Block = Emoticons (range U+1F600..U+1F64F)

### Script

A collection of characters used by one or more writing systems.

-   Some scripts support several writing systems. For example, the Latin
    script supports the writing systems English, French, German, Latin,
    etc.
-   Some languages can be written in multiple alternate writing systems
    that are supported by multiple scripts. For example, Turkish used
    the Arabic script before it transitioned to the Latin script in the
    early 20th century.

1.  Examples

    -   α: Script = Greek
    -   Д: Script = Cyrillic

# Footnotes

[^1]: <https://github.com/tc39/proposal-regexp-unicode-property-escapes>

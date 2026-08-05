---
publish: true
title: JavaScript RegExp Unicode Property Escapes
created: 2020-11-06T09:06:34
modified: 2026-08-05T10:26:50.506Z
---

# JavaScript RegExp Unicode Property Escapes

- [Description](#description)
- [Proposal](#proposal)
- [Syntax](#syntax)
- [Properties](#properties)
  - [Examples](#examples)
    - [Name](#name)
    - [General\_Category](#general_category)
    - [White\_Scpace](#white_scpace)
    - [Age](#age)
    - [Block](#block)
    - [Script](#script)
      - [Examples](#examples-1)
- [Footnotes](#footnotes)

# Description

Characters can be matched by mentioning their Unicode character properties inside of ~\p{}~:

# Proposal

RegExp Unicode Property Escapes\[fn:escapes]

# Syntax

console.log(/^\p{White\_Space}+$/u.test("\t \n\r")); // true
console.log(/^\p{Script=Greek}+$/u.test("μετά")); // true

# Properties

## Examples

### Name

A unique name, composed of uppercase letters, digits, hyphens and spaces.

- A: Name = LATIN CAPITAL LETTER A
- 🙂: Name = SLIGHTLY SMILING FACE

### General\_Category

categorizes characters

- x: General\_Category = Lowercase\_Letter
- \$: General\_Category = Currency\_Symbol

### White\_Scpace

Used for marking invisible spacing characters, such as spaces, tabs and newlines.

- \t: White\_Space = True
- π: White\_Space = False

### Age

Version of the Unicode Standard in which a character was introduced. For example: The Euro sign € was added in version 2.1 of the Unicode standard.

- €: Age = 2.1

### Block

A contiguous range of code points. Blocks don’t overlap and their names are unique.

- S: Block = Basic\_Latin (range U+0000..U+007F)
- 🙂: Block = Emoticons (range U+1F600..U+1F64F)

### Script

A collection of characters used by one or more writing systems.

- Some scripts support several writing systems. For example, the Latin script supports the writing systems English, French, German, Latin, etc.
- Some languages can be written in multiple alternate writing systems that are supported by multiple scripts. For example, Turkish used the Arabic script before it transitioned to the Latin script in the early 20th century.

#### Examples

- α: Script = Greek
- Д: Script = Cyrillic

# Footnotes

\[fn:escapes]https://github.com/tc39/proposal-regexp-unicode-property-escapes

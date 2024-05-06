---
id: 65433588-930a-4386-a010-77240faaca80
title: Pseudo-localization Translator
---

# Description

Pseudolocalization[^1] is a software testing method for testing
internationalization. Instead of translating the text of the software
into a foreign language, the textual elements of an application are
replaced with an altered version of the original language.

These problems can be solved with pseudolocalization, a software testing
method used for testing internationalization. In this method, instead of
translating the text of the software into a foreign language, the
textual elements of an application are replaced with an altered version
of the original language.

For example, `Account Settings` is translated as
`[!!! Àççôûñţ Šéţţîñĝš !!!]`. First, the original text is expanded in
length with characters like `[!!! !!!]` to test the application when
using languages more verbose than the original one. This solves the
first problem.

In addition, the original characters are replaced by similar but
accented characters. This makes the text highly readable, while allowing
to test the application with all kinds of accented and special
characters. This solves the second problem.

# Syntax

``` yaml
# config/packages/translator.yaml
framework:
    translator:
        # ...
        pseudo_localization:
            # replace characters by their accented version
            accents: true
            # wrap strings with brackets
            brackets: true
            # controls how many extra characters are added to make text longer
            expansion_factor: 1.4
            # maintain the original HTML tags of the translated contents
            parse_html: true
            # also translate the contents of these HTML attributes
            localizable_html_attributes: ['title']
```

# Footnotes

[^1]: <https://en.wikipedia.org/wiki/Pseudolocalization>

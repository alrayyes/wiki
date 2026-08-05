---
publish: true
title: Pseudo-localization Translator
created: 2020-11-17T10:01:12
modified: 2026-08-05T10:26:50.513Z
---

# Pseudo-localization Translator

# Description

Pseudolocalization\[fn:pseudo] is a software testing method for testing internationalization. Instead of translating the text of the software into a foreign language, the textual elements of an application are replaced with an altered version of the original language.

These problems can be solved with pseudolocalization, a software testing method used for testing internationalization. In this method, instead of translating the text of the software into a foreign language, the textual elements of an application are replaced with an altered version of the original language.

For example, ~Account Settings~ is translated as ~\[!!! Àççôûñţ Šéţţîñĝš !!!]~. First, the original text is expanded in length with characters like ~\[!!! !!!]~ to test the application when using languages more verbose than the original one. This solves the first problem.

In addition, the original characters are replaced by similar but accented characters. This makes the text highly readable, while allowing to test the application with all kinds of accented and special characters. This solves the second problem.

# Syntax

# config/packages/translator.yaml

framework:
translator:
\# ...
pseudo\_localization:
\# replace characters by their accented version
accents: true
\# wrap strings with brackets
brackets: true
\# controls how many extra characters are added to make text longer
expansion\_factor: 1.4
\# maintain the original HTML tags of the translated contents
parse\_html: true
\# also translate the contents of these HTML attributes
localizable\_html\_attributes: \['title']

# Footnotes

\[fn:pseudo]https://en.wikipedia.org/wiki/Pseudolocalization

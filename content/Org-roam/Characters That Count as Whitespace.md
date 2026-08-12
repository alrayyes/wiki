---
publish: true
title: Characters That Count as Whitespace
created: 2020-11-16T10:09:26
modified: 2026-08-12T09:44:58.315Z
---

# Characters That Count as Whitespace

## Description

Characters that count as whitespace in [[JavaScript Strings]].

## WhiteSpace code points

- \~<TAB>~ (CHARACTER TABULATION, U+0009)
- \~<VT>~ (LINE TABULATION, U+000B)
- \~<FF>~ (FORM FEED, U+000C)
- \~<SP>~ (SPACE, U+0020)
- \~<NBSP>~ (NO-BREAK SPACE, U+00A0)
- \~<ZWNBSP>~ (ZERO WIDTH NO-BREAK SPACE, U+FEFF)
- Any other Unicode character with the property ~White\_Space~ in category Space\_Separator (Zs).

## LineTerminator code points

- \~<LF>~ (LINE FEED, U+000A)
- \~<CR>~ (CARRIAGE RETURN, U+000D)
- \~<LS>~ (LINE SEPARATOR, U+2028)
- \~<PS>~ (PARAGRAPH SEPARATOR, U+2029)

---
publish: true
title: PHP Named Arguments
created: 2020-11-12T11:19:10
modified: 2026-08-05T10:26:50.510Z
---

# PHP Named Arguments

# Description

Allowes named arguments\[fn:rfc] to be used to access parameters in random order, as in \[JavaScript Named parameters]\(JavaScript Named parameters).

# Syntax

function tralala(string $a, string $b, string $c)
{
    echo $a.' '.$b.' '.$c;
}

tralala(b: 'la', c: 'la', a: 'tra');
// tra la la

# Footnotes

\[fn:rfc]https://wiki.php.net/rfc/named\_params

---
publish: true
title: MatchAll Expression
created: 2020-11-16T16:53:24
modified: 2026-08-05T10:26:50.509Z
---

# MatchAll Expression

# Description

Find all instances of a regular expression match, including the index.

# Syntax

const matches = "Here are some numbers: 5 12 88".matchAll(/\d+/g);
for (const match of matches) {
console.log(match);
}

---
publish: true
title: fromRandom()
created: 2020-11-16T14:23:17
modified: 2026-08-05T10:26:50.501Z
---

# fromRandom()

# Description

Generates random alphanumeric strings

# Syntax

$random = ByteString::fromRandom(6);                   // 'g6UkL2'
$randomPin = ByteString::fromRandom(4, '0123456789');  // '7385'
\$randomKey = ByteString::fromRandom(1, 'WASD');        // 'S'

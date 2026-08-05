---
publish: true
title: Uppercase
created: 2020-11-23T10:32:50
modified: 2026-08-05T10:26:50.521Z
---

# Uppercase

# Description

Transforms every string character to uppercase for \[TypeScript Template Literal String Type]\(TypeScript Template Literal String Type).

# Syntax

type EnthusiasticGreeting<T extends string> = `${Uppercase<T>}`

type HELLO = EnthusiasticGreeting<"hello">;
// same as
//   type HELLO = "HELLO";

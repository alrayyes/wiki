---
publish: true
title: Uncapitalize
created: 2020-11-23T10:34:00
modified: 2026-08-05T10:26:50.521Z
---

# Uncapitalize

# Description

Transforms the first string character to lowercase for \[TypeScript Template Literal String Type]\(TypeScript Template Literal String Type).

# Syntax

type UncapitalizedGreeting<T extends string> = `${Uncapitalize<T>}`

type HELLO = CapitalizedGreeting<"Hello">;
// same as
//   type HELLO = "hello";

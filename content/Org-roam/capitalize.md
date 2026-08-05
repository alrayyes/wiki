---
publish: true
title: Capitalize
created: 2020-11-23T10:33:33
modified: 2026-08-05T10:26:50.495Z
---

# Capitalize

# Description

Transforms the first string character to uppercase for \[TypeScript Template Literal String Type]\(TypeScript Template Literal String Type).

# Syntax

type CapitalizedGreeting<T extends string> = `${Capitalize<T>}`

type HELLO = CapitalizedGreeting<"hello">;
// same as
//   type HELLO = "Hello";

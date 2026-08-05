---
publish: true
title: TypeScript Mapped Type
created: 2020-11-24T08:53:35
modified: 2026-08-05T10:26:50.520Z
---

# TypeScript Mapped Type

# Description

A mapped type can create new object types based on arbitrary keys or new object types based on other object types.

# Syntax

type Options = {
\[K in "noImplicitAny" | "strictNullChecks" | "strictFunctionTypes"]?: boolean
};
// same as
//   type Options = {
//       noImplicitAny?: boolean,
//       strictNullChecks?: boolean,
//       strictFunctionTypes?: boolean
//   };

/// 'Partial<T>' is the same as 'T', but with each property marked optional.
type Partial<T> = {
\[K in keyof T]?: T\[K]
};

# Clauses

- \[TypeScript as Clause]\(TypeScript as Clause)

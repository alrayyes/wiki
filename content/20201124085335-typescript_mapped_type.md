---
id: ddb4f555-9119-43eb-ac2f-64ef5d2d8896
title: TypeScript Mapped Type
---

# Description

A mapped type can create new object types based on arbitrary keys or new
object types based on other object types.

# Syntax

``` typescript
type Options = {
    [K in "noImplicitAny" | "strictNullChecks" | "strictFunctionTypes"]?: boolean
};
// same as
//   type Options = {
//       noImplicitAny?: boolean,
//       strictNullChecks?: boolean,
//       strictFunctionTypes?: boolean
//   };
```

``` typescript
/// 'Partial<T>' is the same as 'T', but with each property marked optional.
type Partial<T> = {
    [K in keyof T]?: T[K]
};
```

# Clauses

-   [as](20201124095453-typescript_as_clause)

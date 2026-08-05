---
publish: true
title: TypeScript String Literal Type
created: 2020-11-23T10:05:51
modified: 2026-08-05T07:58:56.719Z
---

# TypeScript String Literal Type

- [Description](#description)
- [Syntax](#syntax)
- [Examples](#examples)
  - [Unions](#unions)
  - [Enums](#enums)
  - [Property names](#property-names)

# Description

Allows a \[JavaScript Strings]\(JavaScript Strings) to be used as a literal type.

# Syntax

```typescript
let foo: 'Hello';
foo = 'Bar'; // Error: "Bar" is not assignable to type "Hello"
```

# Examples

## Unions

This is useful when uses with \[TypeScript Union Type]\(TypeScript Union Type):

```typescript
type CardinalDirection =
    | "North"
    | "East"
    | "South"
    | "West";

function move(distance: number, direction: CardinalDirection) {
    // ...
}

move(1,"North"); // Okay
move(1,"Nurth"); // Error!
```

## Enums

If you want to go nuts you can mock a string based \[TypeScript Enums]\(TypeScript Enums):

```typescript
/** Utility function to create a K:V from a list of strings */
function strEnum<T extends string>(o: Array<T>): {[K in T]: K} {
  return o.reduce((res, key) => {
    res[key] = key;
    return res;
  }, Object.create(null));
}

/**
  * Sample create a string enum
  */

/** Create a K:V */
const Direction = strEnum([
  'North',
  'South',
  'East',
  'West'
])
/** Create a Type */
type Direction = keyof typeof Direction;

/**
  * Sample using a string enum
  */
let sample: Direction;

sample = Direction.North; // Okay
sample = 'North'; // Okay
sample = 'AnythingElse'; // ERROR!
```

## Property names

String types can be uses as property names in \[JavaScript Maps]\(JavaScript Maps) types.

type Options = {
\[K in "noImplicitAny" | "strictNullChecks" | "strictFunctionTypes"]?: boolean
};
// same as
//   type Options = {
//       noImplicitAny?: boolean,
//       strictNullChecks?: boolean,
//       strictFunctionTypes?: boolean
//   };

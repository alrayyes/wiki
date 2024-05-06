---
id: df00306a-289c-4f50-800c-336b2f8d9999
title: TypeScript String Literal Type
---

# Description

Allows a [String](20200922164551-strings) to be used as a literal type.

# Syntax

``` typescript
let foo: 'Hello';
foo = 'Bar'; // Error: "Bar" is not assignable to type "Hello"
```

# Examples

## Unions

This is useful when uses with
[Unions](20200929163219-typescript_union_type):

``` typescript
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

If you want to go nuts you can mock a string based
[Enum](20200930110721-typescript_enums):

``` typescript
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

String types can be uses as property names in
[mapped](20201012093745-javascript_maps) types.

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

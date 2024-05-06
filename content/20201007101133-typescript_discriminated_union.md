---
id: e39eaedb-0e83-430a-a7c4-85bb6f89da77
title: TypeScript Discriminated Union
---

# Description

If your [class](20201009104411-typescript_classes) has a [literal
member](20201002103357-typescript_literal_types) then you can use that
property to discriminate between
[union](20200929163219-typescript_union_type) members.

# Examples

``` typescript
interface Square {
    kind: "square";
    size: number;
}

interface Rectangle {
    kind: "rectangle";
    width: number;
    height: number;
}
type Shape = Square | Rectangle;

function area(s: Shape) {
    if (s.kind === "square") {
        // Now TypeScript *knows* that `s` must be a square ;)
        // So you can use its members safely :)
        return s.size * s.size;
    }
    else {
        // Wasn't a square? So TypeScript will figure out that it must be a Rectangle ;)
        // So you can use its members safely :)
        return s.width * s.height;
    }
}
```

## Exhaustive Checks

Quite commonly you want to make sure that all members of a
[union](20200929163219-typescript_union_type) have some code(action)
against them. You can do that by simply adding a fall through and making
sure that the inferred type in that block is compatible with the
[never](20201007095614-typescript_never_type) type. For example if you
add the exhaustive check you get a nice error:

``` typescript
interface Square {
    kind: "square";
    size: number;
}

interface Rectangle {
    kind: "rectangle";
    width: number;
    height: number;
}

// Someone just added this new `Circle` Type
// We would like to let TypeScript give an error at any place that *needs* to cater for this
interface Circle {
    kind: "circle";
    radius: number;
}

type Shape = Square | Rectangle | Circle;

function area(s: Shape) {
    if (s.kind === "square") {
        return s.size * s.size;
    }
    else if (s.kind === "rectangle") {
        return s.width * s.height;
    }
    else if (s.kind === "circle") {
        return Math.PI * (s.radius **2);
    }
    else {
        // Okay once more
        const _exhaustiveCheck: never = s;
    }
}
```

### Switch

This can also be accomplished with a `switch` statement:

``` typescript
function area(s: Shape) {
    switch (s.kind) {
        case "square": return s.size * s.size;
        case "rectangle": return s.width * s.height;
        case "circle": return Math.PI * s.radius * s.radius;
        default: const _exhaustiveCheck: never = s;
    }
}
```

### Exhaustive checks

Another solution is to write a function that only accepts a
[never](20201007095614-typescript_never_type) and then throws an
[error](20200901105237-error_handling) if its body every executes:

``` typescript
function assertNever(x:never): never {
    throw new Error('Unexpected value. Should have been never.');
}

interface Square {
    kind: "square";
    size: number;
}
interface Rectangle {
    kind: "rectangle";
    width: number;
    height: number;
}
type Shape = Square | Rectangle;

function area(s: Shape) {
    switch (s.kind) {
        case "square": return s.size * s.size;
        case "rectangle": return s.width * s.height;
        // If a new case is added at compile time you will get a compile error
        // If a new value appears at runtime you will get a runtime error
        default: return assertNever(s);
    }
}
```

## Retrospective Versioning

And after you have a bunch of DTOs you realize that name was a poor
choice. You can add versioning retrospectively by creating a new
[union](20200929163219-typescript_union_type) with
[literal](20201002103357-typescript_literal_types) number (or string if
you want) of DTO. Mark the version 0 as undefined and if you have
strictNullChecks enabled it will just work out:

``` typescript
type DTO =
| {
   version: undefined, // version 0
   name: string,
 }
| {
   version: 1,
   firstName: string,
   lastName: string,
}
// Even later
| {
    version: 2,
    firstName: string,
    middleName: string,
    lastName: string,
}

function printDTO(dto:DTO) {
  if (dto.version == null) {
      console.log(dto.name);
  } else if (dto.version == 1) {
      console.log(dto.firstName,dto.lastName);
  } else if (dto.version == 2) {
      console.log(dto.firstName, dto.middleName, dto.lastName);
  } else {
      const _exhaustiveCheck: never = dto;
  }
}
```

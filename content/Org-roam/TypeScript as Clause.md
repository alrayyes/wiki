---
publish: true
title: TypeScript as Clause
created: 2020-11-24T09:54:53
modified: 2026-08-12T09:32:15.641Z
---

# TypeScript as Clause

## Description

Re-map keys in [[TypeScript Mapped Type]]. See the PR[^pr] for more information.

## Syntax

```typescript
type MappedTypeWithNewKeys<T> = {
    [K in keyof T as NewKeyType]: T[K]
    //            ^^^^^^^^^^^^^
    //            This is the new syntax!
}
```

### Leverage template literal types to create property names based off old ones

```typescript
type Getters<T> = {
    [K in keyof T as `get${Capitalize<string & K>}`]: () => T[K]
};

interface Person {
    name: string;
    age: number;
    location: string;
}

type LazyPerson = Getters<Person>;
```

### Filter out keys

```typescript
// Remove the 'kind' property
type RemoveKindField<T> = {
    [K in keyof T as Exclude<K, "kind">]: T[K]
};

interface Circle {
    kind: "circle";
    radius: number;
}

type KindlessCircle = RemoveKindField<Circle>;
// same as
//   type KindlessCircle = {
//       radius: number;
//   };
```

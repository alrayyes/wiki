---
id: 34b7094a-87a7-4424-ac04-f5b7cb4327dc
title: TypeScript as Clause
---

# Description

Re-map keys in [mapped types](20201124085335-typescript_mapped_type).
See the PR\[fn:pr\] for more information.

# Syntax

``` typescript
type MappedTypeWithNewKeys<T> = {
    [K in keyof T as NewKeyType]: T[K]
    //            ^^^^^^^^^^^^^
    //            This is the new syntax!
}
```

## Leverage template literal types to create property names based off old ones

``` typescript
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

## Filter out keys

``` typescript
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

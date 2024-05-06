---
id: 6df4db64-8ad2-4190-9d4e-3e6f77021a31
title: TypeScript Functions
---

# TypeScript 4.0

## Variadic Tuple Types

### Pre 4.0 situation

Consider the following
[function](20201006111125-javascript_function_declerations) using
[Tuples](20200929163624-typescript_tuple_type):

``` javascript
function concat(arr1, arr2) {
    return [...arr1, ...arr2];
}
```

The only way to type this in [TypeScript](20200929161126-typescript)
used to be:

``` typescript
function concat(arr1: [], arr2: []): [];
function concat<A>(arr1: [A], arr2: []): [A];
function concat<A, B>(arr1: [A, B], arr2: []): [A, B];
function concat<A, B, C>(arr1: [A, B, C], arr2: []): [A, B, C];
function concat<A, B, C, D>(arr1: [A, B, C, D], arr2: []): [A, B, C, D];
function concat<A, B, C, D, E>(arr1: [A, B, C, D, E], arr2: []): [A, B, C, D, E];
function concat<A, B, C, D, E, F>(arr1: [A, B, C, D, E, F], arr2: []): [A, B, C, D, E, F];)

function concat<A2>(arr1: [], arr2: [A2]): [A2];
function concat<A1, A2>(arr1: [A1], arr2: [A2]): [A1, A2];
function concat<A1, B1, A2>(arr1: [A1, B1], arr2: [A2]): [A1, B1, A2];
function concat<A1, B1, C1, A2>(arr1: [A1, B1, C1], arr2: [A2]): [A1, B1, C1, A2];
function concat<A1, B1, C1, D1, A2>(arr1: [A1, B1, C1, D1], arr2: [A2]): [A1, B1, C1, D1, A2];
function concat<A1, B1, C1, D1, E1, A2>(arr1: [A1, B1, C1, D1, E1], arr2: [A2]): [A1, B1, C1, D1, E1, A2];
function concat<A1, B1, C1, D1, E1, F1, A2>(arr1: [A1, B1, C1, D1, E1, F1], arr2: [A2]): [A1, B1, C1, D1, E1, F1, A2];
```

### Post 4.0 situation

1.  Tail example

    Consider the following example:

    ``` javascript
    function tail(arg) {
        const [_, ...result] = arg;
        return result
    }
    ```

    TypeScript 4.0 bring 2 changes here.

    1.  Changes

        1.  Generic spreads in tuple types

            The [spreads](20201014094144-spread) in [tuple
            type](20200929163624-typescript_tuple_type) syntax to be
            [generic](20200929163051-typescript_generics):

            ``` typescript
            function tail<T extends any[]>(arr: readonly [any, ...T]) {
                const [_ignored, ...rest] = arr;
                return rest;
            }

            const myTuple = [1, 2, 3, 4] as const;
            const myArray = ["hello", "world"];

            // type [2, 3, 4]
            const r1 = tail(myTuple);

            // type [2, 3, 4, ...string[]]
            const r2 = tail([...myTuple, ...myArray] as const);
            ```

        2.  Rest elements can occur anywhre in a tuple

            [Rest](20200922162500-rest_parameters) elements can occur
            anywhere in a [tuple](20200929163624-typescript_tuple_type),
            not just at the end:

            ``` typescript
            type Strings = [string, string];
            type Numbers = [number, number];

            // [string, string, number, number, boolean]
            type StrStrNumNumBool = [...Strings, ...Numbers, boolean];
            ```

2.  Concat example

    Note that in cases when we [spread](20201014094144-spread) in a type
    without a known length, the resulting type becomes unbounded as
    well, and all the following elements factor into the resulting rest
    element type.

    ``` typescript
    type Strings = [string, string];
    type Numbers = number[]

    // [string, string, ...Array<number | boolean>]
    type Unbounded = [...Strings, ...Numbers, boolean];
    ```

    Therefore the `concat()` example can be typed with:

    ``` typescript
    type Arr = readonly any[];

    function concat<T extends Arr, U extends Arr>(arr1: T, arr2: U): [...T, ...U] {
        return [...arr1, ...arr2];
    }
    ```

# Examples

## Parameter annotations

``` typescript
function tralala(tra: number, la: number) {}
```

## Return type annotation

``` typescript
interface Foo {
    bar: string
}

function tralala(): Foo {
    return {bar: 'tralala'}
}
```

## Optional Parameters

``` typescript
function foo(bar: number, optional?: string) {}
```

``` typescript
function foo(bar: number, optional: string = 'This is an optional string') {}
```

## Overloading

This is for documentation purposes but imho just makes things more
confusing.

``` typescript
// Overloads
function padding(all: number);
function padding(topAndBottom: number, leftAndRight: number);
function padding(top: number, right: number, bottom: number, left: number);
// Actual implementation that is a true representation of all the cases the function body needs to handle
function padding(a: number, b?: number, c?: number, d?: number) {
    if (b === undefined && c === undefined && d === undefined) {
        b = c = d = a;
    }
    else if (c === undefined && d === undefined) {
        c = a;
        d = b;
    }
    return {
        top: a,
        right: b,
        bottom: c,
        left: d
    };
}

padding(1); // Okay: all
padding(1,1); // Okay: topAndBottom, leftAndRight
padding(1,1,1,1); // Okay: top, right, bottom, left

padding(1,1,1); // Error: Not a part of the available overloads
```

## Declaring Functions

Use this to declare function type without providing implementation:

``` typescript
type LongHand = {
    (a: number): number;
};

type ShortHand = (a: number) => number;
```

Overloading is supported as well:

``` typescript
type LongHandAllowsOverloadDeclarations = {
    (a: number): number;
    (a: string): string;
};
```

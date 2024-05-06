---
id: 45c9ba48-85b1-42fe-9992-e683d8f07e47
title: TypeScript Recursive Conditional Types
---

# Description

In [JavaScript](20200613170905-javascript) it's common to see
[functions](20201006111125-javascript_function_declerations) that can
flatten and build up container types at arbitrary levels. Examples of
these are:

-   The `.then()` method on instances of
    [promise](20200911154351-promises). `.then(...)` unwraps each
    promise until it finds a value that's not "fromise-like" and passes
    that value to a [callback](20200911150451-callbacks).
-   The Array [flat](20201113112029-array_prototype_flat) &
    [flatMap](20201113112058-array_prototype_flatmap) prototypes.

Since [TypeScript 4.1](20201123094735-typescript_4_1), TypeScript eases
some restrictions on conditional types, so that they can model those
patterns. Conditional types can immediately reference themselves within
their branches, making it easier to write recursive [type
aliases](20200929163825-typescript_type_alias).

See the PR[^1] for the implementation.

# Examples

## Get the element types of nested arrays

``` typescript
type ElementType<T> =
    T extends ReadonlyArray<infer U> ? ElementType<U> : T;

function deepFlatten<T extends readonly unknown[]>(x: T): ElementType<T>[] {
    throw "not implemented";
}

// All of these return the type 'number[]':
deepFlatten([1, 2, 3]);
deepFlatten([[1], [2, 3]]);
deepFlatten([[1], [[2]], [[[3]]]]);
```

## Awaited type to deeply unwrap Promises

``` typescript
type Awaited<T> = T extends PromiseLike<infer U> ? Awaited<U> : T;

/// Like `promise.then(...)`, but more accurate in types.
declare function customThen<T, U>(
    p: Promise<T>,
    onFulfilled: (value: Awaited<T>) => U
): Promise<Awaited<U>>;
```

# Caveats

Keep in mind that while these recursive types are powerful, but they
should be used responsibly and sparingly.

First off, these types can do a lot of work which means that they can
increase type-checking time. Trying to model numbers in the Collatz
conjecture or Fibonacci sequence might be fun, but don’t ship that in
`.d.ts` files on npm.

Apart from being computationally intensive, these types can hit an
internal recursion depth limit on sufficiently-complex inputs. When that
recursion limit is hit, that results in a compile-time error. In
general, it’s better not to use these types at all than to write
something that fails on more realistic examples.

# Footnotes

[^1]: <https://github.com/microsoft/TypeScript/pull/40002>

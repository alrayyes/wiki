---
publish: true
title: TypeScript Recursive Conditional Types
created: 2020-11-25T08:57:27
modified: 2026-08-05T07:58:56.719Z
---

# TypeScript Recursive Conditional Types

# Description

In [JavaScript](JavaScript) it's common to see \[JavaScript function declarations]\(JavaScript function declarations) that can flatten and build up container types at arbitrary levels. Examples of these are:

- The ~.then()~ method on instances of \[JavaScript Promises]\(JavaScript Promises). ~.then(...)~ unwraps each promise until it finds a value that's not "fromise-like" and passes that value to a \[JavaScript Callbacks]\(JavaScript Callbacks).
- The Array [Array.prototype.flat()](Array.prototype.flat\(\)) & [Array.prototype.flatMap()](Array.prototype.flatMap\(\)) prototypes.

Since \[TypeScript 4.1]\(TypeScript 4.1), TypeScript eases some restrictions on conditional types, so that they can model those patterns. Conditional types can immediately reference themselves within their branches, making it easier to write recursive \[TypeScript Type Alias]\(TypeScript Type Alias).

See the PR\[fn:implementation] for the implementation.

# Examples

## Get the element types of nested arrays

type ElementType<T> =
T extends ReadonlyArray<infer U> ? ElementType<U> : T;

function deepFlatten\<T extends readonly unknown\[]>(x: T): ElementType<T>\[] {
throw "not implemented";
}

// All of these return the type 'number\[]':
deepFlatten(\[1, 2, 3]);
deepFlatten(\[\[1], \[2, 3]]);
deepFlatten(\[\[1], [2](2), \[[3]([3)]]);

## Awaited type to deeply unwrap Promises

type Awaited<T> = T extends PromiseLike<infer U> ? Awaited<U> : T;

/// Like `promise.then(...)`, but more accurate in types.
declare function customThen\<T, U>(
p: Promise<T>,
onFulfilled: (value: Awaited<T>) => U
): Promise\<Awaited<U>>;

# Caveats

Keep in mind that while these recursive types are powerful, but they should be used responsibly and sparingly.

First off, these types can do a lot of work which means that they can increase type-checking time. Trying to model numbers in the Collatz conjecture or Fibonacci sequence might be fun, but don’t ship that in ~.d.ts~ files on npm.

Apart from being computationally intensive, these types can hit an internal recursion depth limit on sufficiently-complex inputs. When that recursion limit is hit, that results in a compile-time error. In general, it’s better not to use these types at all than to write something that fails on more realistic examples.

# Footnotes

\[fn:implementation]https://github.com/microsoft/TypeScript/pull/40002

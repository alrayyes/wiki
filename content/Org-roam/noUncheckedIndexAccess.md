---
publish: true
title: noUncheckedIndexAccess
created: 2020-11-26T10:49:31
modified: 2026-08-12T10:31:55.419Z
---

# noUncheckedIndexAccess

## Default

\~false~

## Description

TypeScript supports [[TypeScript Index Signatures]]. These signatures are a way to signal to the type system that users can access arbitrarily-named properties:

```typescript
interface Options {
    path: string;
    permissions: number;

    // Extra properties are caught by this index signature.
    [propName: string]: string | number;
}

function checkOptions(opts: Options) {
    opts.path // string
    opts.permissions // number

    // These are all allowed too!
    // They have the type 'string | number'.
    opts.yadda.toString();
    opts["foo bar baz"].toString();
    opts[Math.random()].toString();
}
```

When the ~--noUncheckedIndexAccess~ flag is used, every property access (like ~foo.bar~) or indexed access (like ~foo\["bar"]~) that ends up resolving to an index signature is considered potentially undefined. Ie: ~opts.yadda~ will have the type ~string | number | undefined~ as opposed to just ~string | number~. If you need to access that property, you’ll either have to check for its existence first or use a non-null assertion operator (the postfix ~!~ character):

```typescript
// Checking if it's really there first.
if (opts.yadda) {
    console.log(opts.yadda.toString());
}


// Basically saying "trust me I know what I'm doing"
// with the '!' non-null assertion operator.
opts.yadda!.toString();
```

One consequence of using ~--noUncheckedIndexedAccess~ is that indexing into an [[TypeScript Arrays]] is also more strictly checked, even in a bounds-checked loop:

```typescript
function screamLines(strs: string[]) {
    // this will have issues
    for (let i = 0; i < strs.length; i++) {
        console.log(strs[i].toUpperCase());
        //          ~~~~~~~
        // error! Object is possibly 'undefined'.
    }
}
```

If you don’t need the indexes, you can iterate over individual elements by using a [[JavaScript For Of]] loop or a forEach call:

```typescript
function screamLines(strs: string[]) {
    // this works fine
    for (const str of strs) {
        console.log(str.toUpperCase());
    }

    // this works fine
    strs.forEach(str => {
        console.log(str.toUpperCase());
    });
}
```

This flag can be handy for catching out-of-bounds errors, but it might be noisy for a lot of code, so it is not automatically enabled by the ~--strict~ flag. More information can be found in the PR[^pr].

## Footnotes

[^pr]: https://github.com/microsoft/TypeScript/pull/39560

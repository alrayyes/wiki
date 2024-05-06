---
id: 81de1606-f1e2-41e6-a386-103e110436cd
title: noUncheckedIndexAccess
---

# Default

`false`

# Description

TypeScript supports [index signatures](20201008092225-index_signatures).
These signatures are a way to signal to the type system that users can
access arbitrarily-named properties:

``` typescript
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

When the `--noUncheckedIndexAccess` flag is used, every property access
(like `foo.bar`) or indexed access (like `foo["bar"]`) that ends up
resolving to an index signature is considered potentially undefined. Ie:
`opts.yadda` will have the type `string | number | undefined` as opposed
to just `string | number`. If you need to access that property, you’ll
either have to check for its existence first or use a non-null assertion
operator (the postfix `!` character):

``` typescript
// Checking if it's really there first.
if (opts.yadda) {
    console.log(opts.yadda.toString());
}


// Basically saying "trust me I know what I'm doing"
// with the '!' non-null assertion operator.
opts.yadda!.toString();
```

One consequence of using `--noUncheckedIndexedAccess` is that indexing
into an [array](20200929162129-arrays) is also more strictly checked,
even in a bounds-checked loop:

``` typescript
function screamLines(strs: string[]) {
    // this will have issues
    for (let i = 0; i < strs.length; i++) {
        console.log(strs[i].toUpperCase());
        //          ~~~~~~~
        // error! Object is possibly 'undefined'.
    }
}
```

If you don’t need the indexes, you can iterate over individual elements
by using a [for-of](20201030093304-javascript_for_of) loop or a forEach
call:

``` typescript
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

This flag can be handy for catching out-of-bounds errors, but it might
be noisy for a lot of code, so it is not automatically enabled by the
`--strict` flag. More information can be found in the PR[^1].

# Footnotes

[^1]: <https://github.com/microsoft/TypeScript/pull/39560>

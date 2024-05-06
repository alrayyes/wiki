---
id: ab0f6600-4094-4fc6-9bbb-aa4308f81505
title: TypeScript User Defined Type Guards
---

# Syntax

``` typescript
/**
 * Just some interfaces
 */
interface Foo {
    foo: number;
    common: string;
}
​
interface Bar {
    bar: number;
    common: string;
}
​
/**
 * User Defined Type Guard!
 */
function isFoo(arg: any): arg is Foo {
    return arg.foo !== undefined;
}
​
/**
 * Sample usage of the User Defined Type Guard
 */
function doStuff(arg: Foo | Bar) {
    if (isFoo(arg)) {
        console.log(arg.foo); // OK
        console.log(arg.bar); // Error!
    }
    else {
        console.log(arg.foo); // Error!
        console.log(arg.bar); // OK
    }
}
​
doStuff({ foo: 123, common: '123' });
doStuff({ bar: 123, common: '123' });
```

-   [TypeScript Type Guard](20201002102455-typescript_type_guard)

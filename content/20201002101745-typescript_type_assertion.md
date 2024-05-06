---
id: f86e5e6b-8a05-4dc5-9954-743fabef33bc
title: TypeScript Type Assertion
---

# Introduction

If you're a Mr(s). Know It All and want to tell the compiler what to do
you can use `Type Assertions`.

# Syntax

``` typescript
interface Foo {
    bar: number;
    bas: string;
}

var foo = {} as Foo;
foo.bar = 123;
foo.bas = 'hello';
```

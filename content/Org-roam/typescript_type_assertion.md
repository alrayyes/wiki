---
publish: true
title: TypeScript Type Assertion
created: 2020-10-02T10:17:45
modified: 2026-08-05T10:26:50.521Z
---

# TypeScript Type Assertion

- [Introduction](#introduction)
- [Syntax](#syntax)

# Introduction

If you're a Mr(s). Know It All and want to tell the compiler what to do you can use ~Type Assertions~.

# Syntax

```typescript
interface Foo {
    bar: number;
    bas: string;
}

var foo = {} as Foo;
foo.bar = 123;
foo.bas = 'hello';
```

---
id: 894dff80-c2c8-4408-b05f-3079ca833b3c
title: TypeScript Tuple Type
---

# Syntax

## Basic

``` typescript
var nameNumber: [string, number];
var name: string;
var num: number;

// Okay
nameNumber = ['Jenny', 8675309];

// Error!
nameNumber = ['Jenny', '867-5309'];

var [name, num] = nameNumber;
```

## Rest elements

[Rest](20200922162500-rest_parameters) elements can occur anywhere in a
tuple, not just at the end:

``` typescript
type Strings = [string, string];
type Numbers = [number, number];

// [string, string, number, number, boolean]
type StrStrNumNumBool = [...Strings, ...Numbers, boolean];
```

## Labels

``` typescript
type Range = [start: number, end: number];
```

``` typescript
type Foo = [first: number, second?: string, ...rest: any[]];
```

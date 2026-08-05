---
publish: true
title: TypeScript Tuple Type
created: 2020-09-29T16:36:24
modified: 2026-08-05T10:26:50.520Z
---

# TypeScript Tuple Type

- [Syntax](#syntax)
  - [Basic](#basic)
  - [Rest elements](#rest-elements)
  - [Labels](#labels)

# Syntax

## Basic

```typescript
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

\[JavaScript Rest Parameters]\(JavaScript Rest Parameters) elements can occur anywhere in a tuple, not just at the end:

```typescript
type Strings = [string, string];
type Numbers = [number, number];

// [string, string, number, number, boolean]
type StrStrNumNumBool = [...Strings, ...Numbers, boolean];
```

## Labels

```typescript
type Range = [start: number, end: number];
```

```typescript
type Foo = [first: number, second?: string, ...rest: any[]];
```

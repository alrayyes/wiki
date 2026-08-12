---
publish: true
title: TypeScript Enums
created: 2020-09-30T11:07:21
---

## Syntax

```typescript
enum CardSuit {
    Clubs,
    Diamonds,
    Hearts,
    Spades
}

// Sample usage
var card = CardSuit.Clubs;

// Safety
card = "not a member of card suit"; // Error : string is not assignable to type `CardSuit`
```

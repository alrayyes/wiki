---
id: 4e52541b-5119-4228-97b2-f17f5a23b138
title: TypeScript Enums
---

# Syntax

``` typescript
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

---
publish: true
title: ephemeral
created: 2020-11-26T10:03:31
modified: 2026-08-05T10:26:50.500Z
---

# ephemeral

# Origin

Greek ephemeros "lasting only a day".

# Definition

The opposite of persistant.

# Examples

## RAM

- RAM is ephemeral whereas hard disk storage is persistant.

## Data structures

Data structures are ephemeral because properties can be mutated and there's no way to get back the original object

const dinner = {
main: 'turkey',
side: 'potatoes'
}

dinner.side = 'potatoes'

console.log(dinner) // { main: 'turkey', side: 'potatoes' }

## Cloud computing

- AWS Lambda
- Google Cloud Functions

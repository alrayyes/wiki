---
publish: true
title: idempotent
created: 2020-11-26T09:55:25
modified: 2026-08-05T10:26:50.502Z
---

# idempotent

# Origin

Idem is latin for 'same'.

# Definition

An operation or function, that when called multiple times will always produce the same result.

# Examples

## Idempotent

console.log(1 \* 1 \* 1 \* 1)

const set = new Set()

set.add('blaat')
set.add('blaat')
set.add('blaat')

console.log(set) // { 'blaat' }

### Practial examples

- Get, Put & Delete endpoints on a REST api
- Payment operations. Reposting the same form should not result in multiple charges to the customer.

## Non idempotent

console.log(2 \* 2 \* 2 \* 2)

const arr = \[]

arr.push('blaat')
arr.push('blaat')
arr.push('blaat')

console.log(arr) // \[ 'blaat', 'blaat', 'blaat' ]

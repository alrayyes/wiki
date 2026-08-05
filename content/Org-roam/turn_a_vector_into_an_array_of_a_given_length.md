---
publish: true
title: Turn a Vector Into An Array Of a Given Length
created: 2020-11-20T10:46:59
modified: 2026-08-05T07:58:56.717Z
---

# Turn a Vector Into An Array Of a Given Length

# Description

It's possible to convert \[Rust Vectors]\(Rust Vectors) into arrays of a given length.

# Syntax

use std::convert::TryInto;

let v1: Vec<u32> = vec!\[1, 2, 3];

// This will succeed; our vector has a length of three, we're trying to
// make an array of length three.
let a1: \[u32; 3] = v1.try\_into().expect("wrong length");

// But if we try to do it with a vector of length five...
let v2: Vec<u32> = vec!\[1, 2, 3, 4, 5];

// ... this will panic, since we have the wrong length.
let a2: \[u32; 3] = v2.try\_into().expect("wrong length");

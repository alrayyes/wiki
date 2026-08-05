---
publish: true
title: Promise.allSettled
created: 2020-11-16T16:33:27
modified: 2026-08-05T10:26:50.513Z
---

# Promise.allSettled

# Description

Let every request finish no matter if others fail or not.

# Syntax

const promises = \[Promise.resolve(1), Promise.reject(2)];
const \[result1, result2] = await Promise.allSettled(promises);

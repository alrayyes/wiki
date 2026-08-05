---
publish: true
title: Object.fromEntries
created: 2020-11-16T09:51:24
modified: 2026-08-05T07:58:56.699Z
---

# Object.fromEntries

# Given an \[\[id:f1c572d5-868b-4ce0-b1ac-9f7cc32dae3d]\[iterable]] over \[key,value] pairs, ~Object.fromEntries()~ creates an object. It does the opposite of \[\[id:55435d35-26e1-460b-a683-ef346c9972a8]\[Object.entries]]. See the proposal\[fn:proposal] for more information.

# Syntax

console.log(
Object.fromEntries(\[
\["foo", 1],
\["bar", 2],
])
); // { foo: 1, bar: 2 }

# Footnotes

\[fn:proposal]https://github.com/tc39/proposal-object-from-entries

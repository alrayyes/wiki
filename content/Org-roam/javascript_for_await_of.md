---
publish: true
title: JavaScript For Await Of
created: 2020-10-30T09:57:41
modified: 2026-08-05T07:58:56.689Z
---

# JavaScript For Await Of

- [Syntax](#syntax)
- [Rejections](#rejections)

# Syntax

async function f() {
for await (const x of createAsyncIterable(\["a", "b"])) {
console.log(x);
}
}
// Output:
// a
// b

# Rejections

Like ~await~ in \[JavaScript Async Functions]\(JavaScript Async Functions), th eloop throws an exception if ~next()~ returns a rejection:

function createRejectingIterable() {
return {
[Symbol.asyncIterator]() {
return this;
},
next() {
return Promise.reject(new Error("Problem!"));
},
};
}
(async function () {
// (A)
try {
for await (const x of createRejectingIterable()) {
console.log(x);
}
} catch (e) {
console.error(e);
// Error: Problem!
}
})(); // (B)

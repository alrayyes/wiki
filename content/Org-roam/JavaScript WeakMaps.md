---
publish: true
title: JavaScript WeakMaps
created: 2020-10-12T09:47:49
---

## Introduction

A WeakMap is a [[JavaScript Maps]] that doesn’t prevent its keys from being garbage-collected. That means that you can associate data with [[JavaScript Objects]] without having to worry about memory leaks.

## Example

```js
//----- Manage listeners

const _objToListeners = new WeakMap();

function addListener(obj, listener) {
    if (! _objToListeners.has(obj)) {
        _objToListeners.set(obj, new Set());
    }
    _objToListeners.get(obj).add(listener);
}

function triggerListeners(obj) {
    const listeners = _objToListeners.get(obj);
    if (listeners) {
        for (const listener of listeners) {
            listener();
        }
    }
}

//----- Example: attach listeners to an object

const obj = {};
addListener(obj, () => console.log('hello'));
addListener(obj, () => console.log('world'));

//----- Example: trigger listeners

triggerListeners(obj);
```

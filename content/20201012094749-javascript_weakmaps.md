---
id: e06279b3-4488-40b1-b822-fca19b47089a
title: JavaScript WeakMaps
---

# Introduction

A WeakMap is a [Map](20201012093745-javascript_maps) that doesn’t
prevent its keys from being garbage-collected. That means that you can
associate data with [objects](20200826201605-objects) without having to
worry about memory leaks.

# Example

``` javascript
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

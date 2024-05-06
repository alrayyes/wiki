---
id: 94a1d579-bd29-42f0-a6c6-2aa0700703d4
title: JavaScript object getters & setters
---

# Example

``` javascript
const obj = {
    get foo() {
        console.log('GET foo');
        return 123;
    },
    set bar(value) {
        console.log('SET bar to '+value);
    }
};

obj.foo
obj.bar = 'tralala'
```

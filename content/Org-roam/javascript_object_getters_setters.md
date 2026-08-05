---
publish: true
title: JavaScript object getters & setters
created: 2020-10-07T09:34:18
modified: 2026-08-05T10:26:50.505Z
---

# JavaScript object getters & setters

# Example

```js
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

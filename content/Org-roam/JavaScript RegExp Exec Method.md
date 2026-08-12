---
publish: true
title: JavaScript RegExp Exec Method
created: 2020-11-04T10:19:24
modified: 2026-08-12T09:32:15.617Z
---

# JavaScript RegExp Exec Method

exec[^exec] returns ~null~ if no match was found or an object with information about the match otherwise:

```js
let match = /\d+/.exec("one two 100");
console.log(match);
console.log(match.index);
```

## See also

- [[JavaScript RegExp Match Method]]

## Footnotes

[^exec]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/exec

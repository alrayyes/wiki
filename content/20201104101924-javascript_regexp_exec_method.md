---
id: 879b1425-8e59-4a5b-a2d8-08838e193b88
title: JavaScript RegExp Exec Method
---

exec[^1] returns `null` if no match was found or an object with
information about the match otherwise:

``` javascript
let match = /\d+/.exec("one two 100");
console.log(match);
console.log(match.index);
```

# See also

-   [match](20201104102212-javascript_regexp_match_method)

# Footnotes

[^1]: <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/exec>

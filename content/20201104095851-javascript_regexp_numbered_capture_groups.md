---
id: 66a8f9f2-9d57-4467-bf41-a84eb4b3d10d
title: JavaScript RegExp Numbered Capture Groups
---

# Examples

## Subexpressions

When the regular expression contains subexpressions grouped with
parentheses, the text that matched those groups will also show up in the
array. The whole match is always the first element. The next element is
the part matched by the first group (the one whose opening parenthesis
comes first in the expression), then the second group, and so on.

``` javascript
let quotedText = /'([^']*)'/;
console.log(quotedText.exec("she said 'hello'"));
```

## No matches

When a group does not end up being matched at all (for example, when
followed by a question mark), its position in the output array will hold
undefined. Similarly, when a group is matched multiple times, only the
last match ends up in the array.

``` javascript
console.log(/bad(ly)?/.exec("bad"));
console.log(/(\d)+/.exec("123"));
```

# See also

[Named capture
groups](20201104100431-javascript_regexp_named_capture_groups)

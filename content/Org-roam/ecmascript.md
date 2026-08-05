---
publish: true
title: ECMAScript Modules
created: 2020-09-16T17:29:14
modified: 2026-08-05T10:26:50.499Z
---

# ECMAScript Modules

# Syntax

```js
import ordinal from "ordinal";
import {days, months} from "date-names";

export function formatDate(date, format) { /* ... */ }
```

## Default export

```js
export default ["Winter", "Spring", "Summer", "Autumn"];
```

---
publish: true
title: serialization
created: 2020-11-26T10:31:42
---

## Origin

English series "in order"

## Defintion

The process of taking data from one format and converting it to a more generic form that can be used by other programs.

## Example

```js
const data = {
    hello: 'world'
}

JSON.stringify(data)
```

```python
import json

dataFromJS = "{hello: 'world'}"

# parse
x = json.loads(dataFromJS)
```

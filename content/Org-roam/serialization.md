---
publish: true
title: serialization
created: 2020-11-26T10:31:42
modified: 2026-08-05T07:58:56.709Z
---

# serialization

# Origin

English series "in order"

# Defintion

The process of taking data from one format and converting it to a more generic form that can be used by other programs.

# Example

const data = {
hello: 'world'
}

JSON.stringify(data)

import json

dataFromJS = "{hello: 'world'}"

# parse

x = json.loads(dataFromJS)

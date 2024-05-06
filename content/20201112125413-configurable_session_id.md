---
id: 9a6ba6b5-92b8-4422-a31a-3d78ba563ef2
title: Configurable Session ID
---

# Syntax

``` yaml
# config/packages/framework.yaml
framework:
    session:
        # configures the length of the string used for the session ID
        # integer; default = 32; valid values = from 22 to 256 (both inclusive)
        sid_length: 64

        # configures the number of bits in encoded session ID character
        # integer; default = 4; valid values: 4, 5, or 6.
        sid_bits_per_character: 4
```

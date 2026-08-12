---
publish: true
title: Lazy Commands
created: 2020-11-09T14:15:40
modified: 2026-08-12T10:31:55.416Z
---

# Lazy Commands

## Description

From [[Symfony 4.0]] commands are lazily loaded. One broken command won't break all the other commands you have. In order to lazy-load a command do the following:

- Define command as a service
- Add a ~command~ property to the ~console.command~ tag

## Syntax

```yaml
app.command.complex_command:
  # ...
  tags:
    # the value of the 'command' attribute is the name of the command
    # (which is what the user needs to type in to execute it)
    - { name: console.command, command: app:my-command }

    # optionally you can define an alias for the command too
    - { name: console.command, command: app:my-command, alias: 'my-shortcut' }
```

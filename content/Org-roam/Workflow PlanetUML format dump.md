---
publish: true
title: Workflow PlanetUML format dump
created: 2020-11-10T15:40:17
---

# Workflow PlanetUML format dump

In [[Symfony 4.1]] new commands were added to export to the PlanetUML[^planetuml] format:

```shell
 bin/console workflow:dump my_workflow --dump-format=puml | java -jar plantuml.jar -p > my_workflow.png
```

## Footnotes

[^planetuml]: http://plantuml.com/

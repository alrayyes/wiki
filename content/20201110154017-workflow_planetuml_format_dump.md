---
id: 507ab1e2-2e03-4ce1-abfd-91157b681558
title: Workflow PlanetUML format dump
---

In [Symfony 4.1](20201110152518-symfony_4_1) new commands were added to
export to the PlanetUML[^1] format:

``` shell
bin/console workflow:dump my_workflow --dump-format=puml | java -jar plantuml.jar -p > my_workflow.png
```

# Footnotes

[^1]: <http://plantuml.com/>

---
publish: true
title: Workflow PlanetUML format dump
created: 2020-11-10T15:40:17
modified: 2026-08-05T07:58:56.722Z
---

# Workflow PlanetUML format dump

In \[Symfony 4.1]\(Symfony 4.1) new commands were added to export to the PlanetUML\[fn:planetuml] format:

bin/console workflow:dump my\_workflow --dump-format=puml | java -jar plantuml.jar -p > my\_workflow.png

# Footnotes

\[fn:planetuml]http://plantuml.com/

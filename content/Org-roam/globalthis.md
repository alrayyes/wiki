---
publish: true
title: globalThis
created: 2020-11-16T17:05:38
modified: 2026-08-05T07:58:56.684Z
---

# globalThis

# Description

This eases yet another JavaScript pita. Replaces the different global object names:

- \~window~ (browser)
- \~global~ (node)
- \~self~ (web workers)

with ~globalThis~.

# Syntax

if (typeof globalThis.alert === "function") {
globalThis.alert("hi");
}

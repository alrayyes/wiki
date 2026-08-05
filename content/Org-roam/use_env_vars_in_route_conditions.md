---
publish: true
title: Use Env Vars in Route Conditions
created: 2020-11-16T13:16:33
modified: 2026-08-05T07:58:56.720Z
---

# Use Env Vars in Route Conditions

# Syntax

/\*\*

- @Route("/new-feature", condition="env('bool:IS\_FEATURE\_ENABLED') === true")
  \*/
  public function \_\_invoke()
  {
  // this route will only execute when the value of the
  // IS\_FEATURE\_ENABLED env var is TRUE
  }

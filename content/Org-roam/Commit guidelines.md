---
publish: true
title: Commit guidelines
created: 2020-11-15T14:16:20
modified: 2026-08-12T10:31:55.391Z
---

# Commit guidelines

## Commit Message Format

```
<type>(<scope>)<!>: <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

## !

Append after ~<type>(<scope>)~ to show commit has a breaking change (optional)

## Revert

If the commit reverts a previous commit, it should begin with ~revert:~, followed by the header of the reverted commit. In the body it should say: ~This reverts commit <hash>.~, where the hash is the SHA of the commit being reverted.

## Types

- _build_: Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)
- _ci_: Changes to our CI configuration files and scripts (example scopes: Travis, Circle, BrowserStack, SauceLabs)
- _docs_: Documentation only changes
- _feat_: A new feature
- _fix_: A bug fix
- _perf_: A code change that improves performance
- _refactor_: A code change that neither fixes a bug nor adds a feature
- _style_: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
- _test_: Adding missing tests or correcting existing tests

## Subject

The subject contains a succinct description of the change:

- use the imperative, present tense: "change" not "changed" nor "changes"
- don't capitalize the first letter
- no dot (.) at the end

## Footer

The footer should contain any information about _Breaking Changes_ and is also the place to reference GitHub/Gitlab issues that this commit _Closes_.

## Breaking Changes\* should start with the word ~BREAKING CHANGE:~ with a space or two newlines. The rest of the commit message is then used for this.

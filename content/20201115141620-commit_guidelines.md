---
id: e57b1687-eeb8-4d10-b152-015a9d8dcec4
title: Commit guidelines
---

# Commit Message Format

    <type>(<scope>)<!>: <subject>
    <BLANK LINE>
    <body>
    <BLANK LINE>
    <footer>

# !

Append after `<type>(<scope>)` to show commit has a breaking change
(optional)

# Revert

If the commit reverts a previous commit, it should begin with `revert:`,
followed by the header of the reverted commit. In the body it should
say: `This reverts commit <hash>.`, where the hash is the SHA of the
commit being reverted.

# Types

-   **build**: Changes that affect the build system or external
    dependencies (example scopes: gulp, broccoli, npm)
-   **ci**: Changes to our CI configuration files and scripts (example
    scopes: Travis, Circle, BrowserStack, SauceLabs)
-   **docs**: Documentation only changes
-   **feat**: A new feature
-   **fix**: A bug fix
-   **perf**: A code change that improves performance
-   **refactor**: A code change that neither fixes a bug nor adds a
    feature
-   **style**: Changes that do not affect the meaning of the code
    (white-space, formatting, missing semi-colons, etc)
-   **test**: Adding missing tests or correcting existing tests

# Subject

The subject contains a succinct description of the change:

-   use the imperative, present tense: "change" not "changed" nor
    "changes"
-   don't capitalize the first letter
-   no dot (.) at the end

# Footer

The footer should contain any information about **Breaking Changes** and
is also the place to reference GitHub/Gitlab issues that this commit
**Closes**.

**Breaking Changes** should start with the word `BREAKING CHANGE:` with
a space or two newlines. The rest of the commit message is then used for
this.

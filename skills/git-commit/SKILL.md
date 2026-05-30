---
name: git-commit
description: Git commit conventions, reset-first workflow, and quick reference for common commands. Trigger on any Git-related question, such as commits, branches, reset, undo, conflicts, and more.
---

# Git Commit Messages

## Overview

Generate semantically accurate commit messages.
If the general convention conflicts with the repository's own commit conventions, always follow the repository rules first.

## Workflow

1. Inspect the changes before writing the commit message.

2. Prefer reading the repository's local rules first. If the repository does not define any rules, use the following format to write the commit message:

```
<type>(<scope>): <subject>
```

3. Choose the most accurate `type`.
   Prefer repository-defined types first. If the repository does not define its own types, `type` can only be one of:

```
feat, fix, style, docs, perf, chore, revert, build, refactor
```

4. Write the `subject` in Angular style.
   Keep it imperative, specific, and without a trailing period.
   Unless the subject begins with a proper noun, brand name, or identifier, prefer lowercase after `type(scope):`.

5. Self-check against the repository rules before returning. If the repository has no self-check rules, use the following:

- The `subject` length must be between `1` and `50` characters.
- `type!:` and `type(scope)!:` are allowed for breaking changes.
- `scope` is optional; omit it if it does not improve clarity.
- Use the `revert:` prefix only when the commit truly reverts an earlier commit.

## Commit Types

| Type       | When to use it                                                                   |
| ---------- | -------------------------------------------------------------------------------- |
| `feat`     | Add a new feature, branch, or content                                            |
| `fix`      | Fix a bug or error                                                               |
| `style`    | Change styles or formatting without changing logic                               |
| `docs`     | Documentation-only changes                                                       |
| `perf`     | Performance improvements                                                         |
| `chore`    | Changes that do not fit a more specific type                                     |
| `revert`   | Revert a previous change or branch                                               |
| `build`    | Changes to build flow, packaging logic, build tooling, or dependency build steps |
| `refactor` | Code refactoring that neither adds features nor fixes bugs                       |
| `test`     | Add or modify test code                                                          |
| `ci`       | Modify the continuous integration configuration                                  |

## Subject Rules

- Use the structure `type(scope): subject` or `type(scope)!: subject`.
- Use lowercase, no period, and imperative mood.
- Keep it concise and readable.
- If the changes include multiple pieces of work, advise splitting them into separate commits.
- Avoid vague messages such as `update file`, `add file`, or `fix bug`.
- Use `!` only when the change introduces a breaking API, breaking behavior, or breaking contract.

## Examples

```
feat(auth): add JWT token refresh mechanism
```

```
fix: resolve race condition in database connection pool
```

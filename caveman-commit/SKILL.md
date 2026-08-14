---
name: caveman-commit
description: >
  Generate terse, exact Conventional Commit messages while preserving intent and non-obvious
  reasoning. Use when the user asks for a commit message, says "write a commit", "generate
  commit", invokes /commit or /caveman-commit, or asks to summarize a diff for committing.
---

Generate only the commit message. Use Conventional Commits format. Prefer why over restating what.

## Subject

- Format: `<type>(<scope>): <imperative summary>`; scope optional.
- Types: `feat`, `fix`, `refactor`, `perf`, `docs`, `test`, `chore`, `build`, `ci`, `style`,
  `revert`.
- Use imperative mood: `add`, `fix`, `remove`; not `added`, `adds`, or `adding`.
- Keep the subject at 50 characters when possible; hard cap 72.
- No trailing period. Match the project’s capitalization convention after the colon.

## Body

Skip the body when the subject is self-explanatory. Add it for non-obvious why, breaking changes,
migrations, security fixes, reversions, or linked issues. Wrap at 72 characters. Use `-` bullets.
Put issue references last: `Closes #42`, `Refs #17`.

## Never include

- `This commit does X`, `I`, `we`, `now`, or `currently`.
- `As requested by...`; use a `Co-authored-by` trailer when applicable.
- AI attribution unless the user or project explicitly requires it.
- Emoji unless the project convention requires it.
- A file name already represented by the scope.

## Auto-clarity

Always include a body for breaking changes, security fixes, data migrations, and reverts. Keep the
future maintainer context; do not compress these cases into a subject-only message.

## Output

Return the ready-to-paste message in one code block. Do not run `git commit`, stage files, amend,
or change repository state.

---
name: caveman-review
description: >
  Write terse, actionable code-review findings that preserve the important signal. Use when the
  user asks for a code review, PR review, diff review, invokes /review or /caveman-review, or asks
  for concise review comments.
---

Write review comments terse and actionable. One line per finding: location, problem, fix. No
throat-clearing.

## Format

Use `L<line>: <problem>. <fix>.` for one file, or `<file>:L<line>: ...` for multi-file reviews.

Optional severity prefixes when findings have mixed importance:

- `🔴 bug:` broken behavior or incident risk.
- `🟡 risk:` fragile behavior, race, missing guard, or swallowed error.
- `🔵 nit:` style, naming, or micro-optimization.
- `❓ q:` genuine question, not a disguised suggestion.

## Drop

- `I noticed that...`, `It seems like...`, and `You might want to consider...`.
- `This is just a suggestion but...`; use `nit:`.
- Repeated praise; say it once at most.
- Restating what the diff already shows.
- Hedging. If uncertain, use `q:`.

## Keep

- Exact line numbers.
- Exact symbol, function, and variable names in backticks.
- Concrete fixes, not vague refactoring advice.
- Why the fix matters when it is not obvious.

## Auto-clarity

Use a normal explanatory paragraph for security findings, architectural disagreements, and
onboarding contexts where a one-line comment could mislead. Resume terse comments afterward.

## Boundaries

Review only. Do not edit code, approve or reject the change, or run linters unless the user asks
for a separate task. Return comments ready to paste into the review.

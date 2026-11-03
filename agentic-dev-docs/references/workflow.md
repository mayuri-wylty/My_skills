# Workflow Reference

## Standard phases
1. User gives initial project idea.
2. Agent asks for missing project-design requirements.
3. User replies with requirements.
4. Agent summarizes requirements, adds missing considerations, and proposes multi-agent collaboration options.
5. User confirms suggestions and selects a collaboration option.
6. Agent freezes key decisions and produces a decision-complete plan.
7. User confirms and executes the plan.
8. Agent generates development-control docs only.
9. User opens a new vibe coding session.
10. New session reads `总控开发入口.md`, recognizes itself as A main controller, creates selected subagents, and coordinates development.

## Frozen decisions
Freeze before doc generation:
- MVP scope
- explicit non-goals
- tech stack
- docs directory
- code directory
- selected subagent topology
- serial/parallel rules
- progress ownership
- testing/review gates
- audit gates
- final acceptance rule
- subagent model and reasoning-effort defaults
- human-blocking skip and retry policy
- local commit and remote-push policy

## Non-execution gate
During discovery, collaboration design, plan generation, and docs generation:
- no product code
- no scaffolding
- no dependency installation
- no dev server
- no codegen into product directories

## Contract-first rule
For projects with APIs, modules, data stores, CLI inputs, or external services:

```text
A assigns contract task -> relevant worker drafts contract -> review worker reviews contract -> A freezes contract -> implementation workers implement against contract
```

Contract examples:
- API routes and request/response shapes
- database schema
- config schema
- log schema
- event format
- CLI arguments and output format
- file naming and directory conventions

## Audit gates
Recommended gates:
- after project skeleton
- after core feature implementation
- after integration
- before final handoff

Final audit is mandatory. The auditor may be called D, but the label is not mandatory.

## Human-blocking policy

When a task requires developer or user intervention, A records `BLOCKED-HUMAN`, the exact reason, impact, attempted actions, required input, owner, and retry condition. A skips only the blocked point, continues independent work, and retries at a phase boundary, dependency change, or arrival of the required input. A does not mark blocked work complete.

## Commit and push policy

After an independently testable task passes verification, the responsible workstream may create a local commit and record its hash in progress. `git push`, pull-request creation, and remote branch operations require explicit plan or user authorization.

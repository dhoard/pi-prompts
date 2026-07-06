# Java Prompt Templates

Pi-compatible and project-agnostic prompt templates for structured Java software
engineering workflows. Every prompt is self-contained and uses pi's
`$ARGUMENTS` variable for parameterization.

## Prompt Index

| File | Purpose | Use When |
|---|---|---|
| `planning-workflow.md` | Plan file naming convention | You need a durable plan file and want consistent naming |
| `design-interview.md` | Structured design interview | You have a problem statement and need to resolve all design decisions before writing a plan |
| `create-design-plan.md` | Design plan document | You have a resolved design and need to document the approach, tradeoffs, and test strategy |
| `create-implementation-spec.md` | Implementation specification | You have a design plan and need step-by-step implementation instructions |
| `implement-spec.md` | Execute an implementation spec | You have a complete implementation specification and are ready to write code |
| `analyze-code.md` | Correctness and bug analysis | You need a focused bug-hunt on a module without writing any code |
| `java-code-review.md` | Java code review | You need a comprehensive engineering review of Java code |
| `java-code-coverage.md` | Java coverage improvement | You want one safe, deterministic iteration to improve test coverage |
| `java-performance-review.md` | Java performance review | You have profile or benchmark data and need performance recommendations |
| `fix-code-loop.md` | Full analysis-to-implementation loop | You want to find and fix correctness issues in one end-to-end pass |
| `fix-code-loop-10.md` | 10-loop fix across all modules | You want to run 10 consecutive fix loops across the entire project |
| `fix-code-loop-100.md` | 100-loop fix across all modules | You want to run 100 consecutive fix loops across the entire project |
| `coding-principles.md` | Engineering discipline | Reference for coding agent behavior and decision-making |

## Workflow Sequence

The primary design-to-implementation workflow:

```
Problem Statement
      │
      ▼
design-interview.md ──► Resolve all design decisions
      │
      ▼
create-design-plan.md ──► Document approach, tradeoffs, test strategy
      │
      ▼
create-implementation-spec.md ──► Step-by-step implementation instructions
      │
      ▼
implement-spec.md ──► Write the code
      │
      ▼
analyze-code.md ──► Verify correctness (optional review pass)
```

Standalone prompts (use independently):

```
java-code-review.md ──► Comprehensive Java code review (any time)
java-code-coverage.md ──► One focused coverage improvement iteration
java-performance-review.md ──► Performance analysis from profile data
fix-code-loop.md ──► Single analysis-to-implementation loop
fix-code-loop-10.md ──► Ten consecutive fix loops
fix-code-loop-100.md ──► One hundred consecutive fix loops
planning-workflow.md ──► Reference for plan file naming (not an executable prompt)
coding-principles.md ──► Engineering discipline reference
```

## Template Structure

Prompts follow a consistent pattern tailored to their purpose:

- **Design workflow prompts** (`design-interview.md`, `create-design-plan.md`,
  `create-implementation-spec.md`, `implement-spec.md`, `analyze-code.md`)
  follow: Objective → Input → Prerequisites → Stop Conditions →
  Deliverables → Completion Criteria.

- **Playbook prompts** (`java-code-review.md`, `java-code-coverage.md`,
  `java-performance-review.md`) follow: Objective → Priorities/Rules →
  Project Context → Workflow → Output Format.

- **Orchestration prompts** (`fix-code-loop.md`, `fix-code-loop-10.md`,
  `fix-code-loop-100.md`) follow: Execution Boundary → Objective → Input →
  Phase Definitions → Stop Conditions → Completion Criteria.

## Design Principles

- **pi-native**: Uses pi's `$ARGUMENTS` variable for parameterization; no model
  names, provider names, or LLM-specific capabilities. The `design-interview.md`
  prompt handles both multi-turn and single-turn runtimes via branching instructions.
- **Project-agnostic**: No project names, module paths, or tool-specific commands.
  References to build commands, test commands, or conventions use generic placeholders
  (e.g., "the project's agent instructions").
- **Tooling-agnostic**: No editor commands, file-system verbs like "open an editor,"
  or IDE features.
- **Self-contained**: Every prompt contains all the context it needs to be used.
  Drop it into any LLM runtime and it works.

## License

[MIT](../LICENSE)

---

Copyright (c) 2026-present Douglas Hoard

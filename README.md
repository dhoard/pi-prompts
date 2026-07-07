# pi-prompts

A collection of pi-compatible, project-agnostic prompt templates for structured
software engineering workflows. Every executable prompt is self-contained and
uses pi's `$ARGUMENTS` variable for parameterization.

## Canonical Prompt Roots

| Directory | Description |
|---|---|
| [`go/`](go/) | Prompt templates for Go software engineering workflows |
| [`java/`](java/) | Prompt templates for Java software engineering workflows |

Each language directory contains its own `README.md` with a prompt index,
workflow sequence, and usage guidance.

## Prompt Quality Documents

- [`PROMPT_CONTRACT.md`](PROMPT_CONTRACT.md) defines the mandatory contract for
  executable prompts and reference documents.
- [`PROMPT_REVIEW_CHECKLIST.md`](PROMPT_REVIEW_CHECKLIST.md) defines the review
  checklist for determinism, side-effect safety, and Go/Java prompt parity.

## Design Principles

- **pi-native** — Executable prompts use `$ARGUMENTS` as the only required
  substitution variable.
- **Pi agent harness focused** — Prompts are plain markdown templates that work
  in the pi harness without requiring provider-specific runtime features.
- **LLM/provider agnostic** — Prompts do not require a specific model family,
  hosted service, editor, browser, shell, or IDE.
- **Project-agnostic** — Prompts avoid project names, module paths, and
  repository-specific assumptions.
- **Tooling-aware but not tooling-bound** — Prompts prefer commands discovered
  from the target repository. Generic command examples are illustrative unless
  the target repository confirms them.
- **Self-contained and bounded** — Executable prompts define their input,
  execution boundary, stop conditions, output format, and final response.

## Executable Prompts vs References

Most files in `go/` and `java/` are executable prompt templates. Reference
files such as `coding-principles.md` and `planning-workflow.md` provide reusable
guidance and may omit `$ARGUMENTS` because they are not standalone workflows.

## License

[MIT](LICENSE)

---

Copyright (c) 2026-present Douglas Hoard

# Prompt Contract

This contract applies to executable prompt templates in the canonical prompt
roots `go/` and `java/`. Reference documents may omit executable input, but they
must identify themselves as references.

## 1. Pi Harness Input

- Executable prompts use `$ARGUMENTS` as the external input placeholder.
- Do not introduce other required template variables.
- Reference documents may omit `$ARGUMENTS` only when they are not intended to
  be run directly as workflows.

## 2. Provider and Runtime Agnosticism

- Do not require a specific LLM provider, model family, hosted service, editor,
  browser, shell, IDE, or proprietary runtime capability.
- It is acceptable to refer generically to an agent, an LLM runtime, the pi
  harness, project guidance, repository guidance, or agent instructions.
- Prefer capability-neutral wording such as "inspect files", "run validation",
  or "ask for clarification".

## 3. Self-Contained Operation

- Each executable prompt must contain enough instructions to be used on its own.
- A prompt may refer to repository guidance or project agent instructions, but
  required behavior must not depend on hidden state or another prompt file.
- Shared conventions should be repeated where they materially affect behavior.

## 4. Input Handling

- Define valid input forms for each executable prompt.
- If the input is missing, vague, conflicting, or insufficient, require a
  clarification request or blocker report instead of inventing details.
- If repository evidence contradicts the input, report the conflict and stop
  unless the prompt explicitly allows a bounded assumption.

## 5. Repository Inspection

- Prompts that analyze, plan, specify, or implement repository changes must
  require reading the relevant source, tests, configuration, and repository
  guidance before conclusions or edits.
- Every finding, plan claim, or implementation decision must be tied to
  repository evidence or marked as an assumption.
- Do not fabricate files, behavior, APIs, commands, or test results.

## 6. Execution Boundary

- Every executable prompt must state whether it is read-only, writes one
  artifact, or may modify code, tests, and documentation.
- Write-capable prompts must state allowed write scope and prohibit unrelated
  changes.
- Artifact-writing prompts must protect existing files from accidental
  overwrite unless replacement is explicitly requested.

## 7. Commands and Side Effects

- Prefer commands discovered from project guidance, repository documentation,
  or build files.
- Generic language commands may appear only as clearly labeled examples or
  defaults to adapt to the target repository.
- Do not require network access, dependency downloads, browser actions, editor
  actions, commits, pushes, releases, or other external side effects unless the
  user explicitly requested them or the target repository documents them.

## 8. Deterministic Output

- Use explicit, stable headings in a fixed order.
- Mandatory empty sections must say `None` or `Not applicable`.
- Findings must include severity, exact file path, relevant symbol or section,
  evidence, impact, trigger scenario, recommended fix, and validation.
- Plans and specifications must include exact files, behavior rules,
  compatibility impact, error or exception handling, concurrency/lifecycle
  handling, test strategy, and acceptance criteria when relevant.

## 9. Stop Conditions

- Define when to stop, ask for clarification, or report a blocker.
- Stop rather than guessing when required context is unavailable.
- Keep uncertain observations in `Needs confirmation`, `Open Questions`, or
  `Blockers` instead of silently resolving them.

## 10. Final Response Discipline

- Artifact-writing prompts must specify the final response content.
- Implementation prompts must report changed files, validation results,
  blockers, and assumptions.
- Read-only prompts must not claim to have changed files or run commands unless
  the prompt explicitly allowed and required those actions.

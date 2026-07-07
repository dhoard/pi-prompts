# Prompt Review Checklist

Use this checklist when adding or changing prompt templates in `go/` and
`java/`.

## Executable Prompt Basics

- [ ] The prompt has a clear objective.
- [ ] The input section contains `$ARGUMENTS`.
- [ ] Valid input forms are described.
- [ ] Missing, vague, conflicting, or insufficient input is handled by a
      clarification request or blocker.
- [ ] The prompt is self-contained and does not depend on hidden runtime state.

## Execution Boundary

- [ ] The prompt states whether it is read-only, artifact-writing, or
      implementation-capable.
- [ ] Allowed writes are explicitly scoped.
- [ ] Existing files are protected from accidental overwrite.
- [ ] Unrelated code, test, config, generated-file, and documentation changes
      are prohibited unless explicitly in scope.

## Deterministic Output

- [ ] Required sections are named and ordered.
- [ ] Mandatory empty sections require `None` or `Not applicable`.
- [ ] Findings require severity, path, symbol, evidence, impact, trigger,
      recommended fix, and validation.
- [ ] Plans/specs require files, behavior rules, compatibility, error or
      exception handling, concurrency/lifecycle, tests, and acceptance criteria.
- [ ] Final response content is defined for prompts that write or modify files.

## Evidence and Stop Conditions

- [ ] Repository inspection is required before conclusions or edits.
- [ ] Findings and design claims must cite repository evidence or state an
      assumption.
- [ ] `Needs confirmation`, `Open Questions`, and `Blockers` are used for
      uncertainty.
- [ ] The prompt stops rather than guessing when required context is unavailable.

## Provider and Runtime Agnosticism

- [ ] No specific LLM provider, model family, hosted service, editor, IDE,
      browser, shell, or proprietary runtime feature is required.
- [ ] Commands are discovered from project guidance when possible.
- [ ] Generic commands are labeled as examples or defaults.
- [ ] Network access, dependency installation, commits, pushes, and releases are
      gated by explicit user or repository instruction.

## Go/Java Pair Parity

For each paired prompt, verify equivalent workflow semantics while preserving
language terminology:

- [ ] `go/analyze-code.md` and `java/analyze-code.md`
- [ ] `go/coding-principles.md` and `java/coding-principles.md`
- [ ] `go/create-design-plan.md` and `java/create-design-plan.md`
- [ ] `go/create-implementation-spec.md` and `java/create-implementation-spec.md`
- [ ] `go/design-interview.md` and `java/design-interview.md`
- [ ] `go/fix-code-loop.md` and `java/fix-code-loop.md`
- [ ] `go/fix-code-loop-10.md` and `java/fix-code-loop-10.md`
- [ ] `go/fix-code-loop-100.md` and `java/fix-code-loop-100.md`
- [ ] `go/implement-spec.md` and `java/implement-spec.md`
- [ ] `go/planning-workflow.md` and `java/planning-workflow.md`

## README and Index Accuracy

- [ ] `README.md` identifies `go/` and `java/` as canonical prompt roots.
- [ ] Language READMEs list every prompt in their directory.
- [ ] Executable prompts and reference documents are distinguished.
- [ ] Links to `PROMPT_CONTRACT.md` and this checklist are accurate.

## Scenario Validation

- [ ] Vague problem statements lead to a blocker or clarification request.
- [ ] Design-plan prompts produce only design-plan artifacts.
- [ ] Implementation-spec prompts require reproduction-first or
      missing-behavior-first validation steps.
- [ ] Implementation prompts stop on ambiguous specifications.
- [ ] Analysis/review prompts report only evidence-backed findings.
- [ ] Fix-loop prompts stop when no confirmed bounded issue exists.
- [ ] Coverage prompts perform one focused iteration only.

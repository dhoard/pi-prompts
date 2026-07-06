# pi-prompts

A collection of pi-compatible, project-agnostic prompt templates for structured software engineering workflows. Every prompt is self-contained and uses pi's `$ARGUMENTS` variable for parameterization.

## Languages

| Directory | Description |
|---|---|
| [`go/`](go/) | Prompt templates for Go software engineering workflows |
| [`java/`](java/) | Prompt templates for Java software engineering workflows |

Each language directory contains its own `README.md` with a full prompt index, workflow sequence, and usage guidance.

## Design Principles

- **pi-native** — Uses pi's `$ARGUMENTS` variable for parameterization; no model names, provider names, or LLM-specific capabilities.
- **Project-agnostic** — No project names, module paths, or tool-specific commands.
- **Tooling-agnostic** — No editor commands, file-system verbs, or IDE features.
- **Self-contained** — Every prompt contains all the context it needs to be used.

## License

[MIT](LICENSE)

# pi-prompts

A collection of LLM-agnostic, project-agnostic prompt templates for structured software engineering workflows. Every prompt is self-contained — drop it into any LLM runtime or coding agent and it works without additional context.

## Languages

| Directory | Description |
|---|---|
| [`go/`](go/) | Prompt templates for Go software engineering workflows |
| [`java/`](java/) | Prompt templates for Java software engineering workflows |

Each language directory contains its own `README.md` with a full prompt index, workflow sequence, and usage guidance.

## Design Principles

- **LLM-agnostic** — No model names, provider names, or LLM-specific capabilities.
- **Project-agnostic** — No project names, module paths, or tool-specific commands.
- **Tooling-agnostic** — No editor commands, file-system verbs, or IDE features.
- **Self-contained** — Every prompt contains all the context it needs to be used.

## License

[MIT](LICENSE)

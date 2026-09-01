# Cognition Guardrail

[简体中文](README.zh-CN.md)

> Early release: `cognition-guardrail-v0.1.0`

Cognition Guardrail helps preserve human judgment and understanding while an AI coding agent completes technical work. It makes important decisions, evidence, assumptions, blind spots, and understanding gaps inspectable without turning every task into a lesson.

## What it does

- Routes work by cognition density rather than file type or task size.
- Keeps mechanical work fast in Production Mode.
- Adds a compact Cognition Delta when a limited decision deserves explanation.
- Uses Learning Mode for difficult diagnosis, interacting mechanisms, and consequential trade-offs.
- Distinguishes demonstrated understanding, a specific misconception, and unverified understanding from observable evidence.
- Uses structurally changed transfer questions so fluent repetition is not mistaken for independent application.
- Keeps exercises optional and separate from task completion.
- Preserves the task's existing scope, permissions, and safety requirements.

## Modes

| Mode | Behavior |
| --- | --- |
| `auto` | Chooses the lightest suitable behavior from the task's cognition density. |
| `production` | Completes the work efficiently and surfaces at most three important cognition items. |
| `learning` | Completes the work and adds a focused preview, audit, and optional transfer check. |

## Install

Clone or download this repository, then copy the Skill directory into the personal skills directory for your agent.

### OpenAI Codex

```bash
mkdir -p ~/.codex/skills
cp -R skills/cognition-guardrail ~/.codex/skills/
```

Ask Codex to use `cognition-guardrail`, optionally specifying `auto`, `production`, or `learning`.

### Claude Code

```bash
mkdir -p ~/.claude/skills
cp -R skills/cognition-guardrail ~/.claude/skills/
```

Invoke it directly:

```text
/cognition-guardrail learning <task>
```

These commands create independent installation copies. They do not add synchronization or modify Git configuration.

## Example routing

- Renaming a local variable with no unresolved judgment: Production, normally without cognition output.
- Changing a DTO compatibility contract: potentially Learning, despite a small diff.
- Diagnosing an intermittent concurrency failure: Learning.
- An explicitly urgent incident: Production until stabilization.

## Limits

The Skill reports concise, inspectable decision rationale, evidence, assumptions, and alternatives. It does not claim to reveal the model's hidden internal step-by-step reasoning, certify mastery, guarantee long-term retention, or authorize implementation and production changes that the user did not request. A second review by the same AI is not treated as independent verification.

## Inspiration

This Skill was shaped by the author's own reflections and by:

- Lars Faye, [AI Coding will Prevent Expertise](https://larsfaye.com/articles/ai-coding-will-prevent-expertise)
- Aaron Gray, [AI and Chauffeur Knowledge](https://www.aaron-gray.com/ai-and-chauffeur-knowledge/)

The articles inspired the problem framing; the Skill's modes, evidence model, permission boundaries, and workflow are its own design.

## License

[MIT](../../LICENSE)

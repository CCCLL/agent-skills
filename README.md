# Agent Skills

[简体中文](README.zh-CN.md)

[![Validate Agent Skills](https://github.com/CCCLL/agent-skills/actions/workflows/validate-skills.yml/badge.svg)](https://github.com/CCCLL/agent-skills/actions/workflows/validate-skills.yml)

A personal collection of portable Agent Skills created and maintained by [CCCLL](https://github.com/CCCLL).

## Skills

| Skill | Purpose | Status |
| --- | --- | --- |
| [cognition-guardrail](skills/cognition-guardrail/README.md) | Makes important engineering decisions and understanding gaps visible while technical work is completed. | Early release |

## Repository layout

```text
skills/
└── cognition-guardrail/
    ├── README.md
    ├── README.zh-CN.md
    └── SKILL.md
```

Each directory under `skills/` is a self-contained Agent Skill. Human-facing documentation lives beside the installable `SKILL.md`.

## Compatibility

The published skills are validated structurally against the [Agent Skills specification](https://agentskills.io/specification). Compatibility is documented per skill. Other Agent Skills clients may work but are not claimed as verified unless listed.

## Safety

Read a Skill and any bundled scripts before installing it. Agent Skills run as instructions within the permissions already granted to the agent.

## License

This repository is licensed under the [MIT License](LICENSE).

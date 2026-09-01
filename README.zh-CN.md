# Agent Skills

[English](README.md)

[![Validate Agent Skills](https://github.com/CCCLL/agent-skills/actions/workflows/validate-skills.yml/badge.svg)](https://github.com/CCCLL/agent-skills/actions/workflows/validate-skills.yml)

这是 [CCCLL](https://github.com/CCCLL) 创建并维护的个人 Agent Skills 作品集，关注可移植、可检查的 Agent 工作方式。

## Skills

| Skill | 用途 | 状态 |
| --- | --- | --- |
| [cognition-guardrail](skills/cognition-guardrail/README.zh-CN.md) | 在完成技术工作的同时，让重要工程决策与理解缺口保持可见。 | 早期版本 |

## 仓库结构

```text
skills/
└── cognition-guardrail/
    ├── README.md
    ├── README.zh-CN.md
    └── SKILL.md
```

`skills/` 下的每个目录都是一个独立的 Agent Skill。面向使用者的说明与可安装的 `SKILL.md` 放在同一目录。

## 兼容性

仓库中的 Skills 会按照 [Agent Skills 规范](https://agentskills.io/specification)进行结构校验。具体兼容范围记录在各 Skill 的说明中；未明确列出的 Agent Skills 客户端可能适用，但尚未验证。

## 安全

安装前请阅读 Skill 及其附带的所有脚本。Agent Skills 会在你已经授予 Agent 的权限范围内作为指令运行。

## 许可证

本仓库采用 [MIT License](LICENSE)。

# Cognition Guardrail

[English](README.md)

> 早期版本：`cognition-guardrail-v0.1.0`

Cognition Guardrail 用于在 AI 编码 Agent 完成技术工作的同时，保留人的判断与理解。它让重要决策、证据、假设、盲点和理解缺口可以被检查，同时避免把每项任务都变成教学流程。

## 它会做什么

- 根据任务的认知密度路由，而不是根据文件类型或任务大小判断。
- 在 Production Mode 中保持机械任务的执行效率。
- 当少量决策值得解释时，输出精简的 Cognition Delta。
- 对困难诊断、相互作用的机制和重要权衡使用 Learning Mode。
- 根据可观察证据区分“在此处已展示理解”“在此处需要纠正”和“尚未验证”。
- 使用结构发生变化的迁移问题，避免把流利复述误判为独立应用。
- 练习保持可选，并与任务是否完成分开判断。
- 保留任务原有的范围、权限和安全要求。

## 模式

| 模式 | 行为 |
| --- | --- |
| `auto` | 根据任务的认知密度选择最轻量且合适的行为。 |
| `production` | 高效完成任务，并最多呈现三个重要认知项。 |
| `learning` | 完成任务，并增加聚焦的预览、审计和可选迁移检查。 |

## 安装

克隆或下载本仓库，然后将 Skill 目录复制到对应 Agent 的个人 Skills 目录。

### OpenAI Codex

```bash
mkdir -p ~/.codex/skills
cp -R skills/cognition-guardrail ~/.codex/skills/
```

让 Codex 使用 `cognition-guardrail`，并可按需指定 `auto`、`production` 或 `learning`。

### Claude Code

```bash
mkdir -p ~/.claude/skills
cp -R skills/cognition-guardrail ~/.claude/skills/
```

直接调用：

```text
/cognition-guardrail learning <任务>
```

这些命令只创建彼此独立的安装副本，不建立同步关系，也不会修改 Git 配置。

## 路由示例

- 只修改局部变量名且不存在未决判断：Production，通常不输出认知内容。
- 修改 DTO 兼容性契约：即使 diff 很小，也可能进入 Learning。
- 诊断间歇性并发故障：Learning。
- 明确的紧急事故：稳定前使用 Production。

## 限制

该 Skill 会提供精简、可核查的决策理由、证据、假设和备选方案，但不会要求或声称展示模型内部隐藏的逐步推理过程。它不会认证“已经掌握”，不保证长期记忆，也不会授权用户未要求的实现或生产环境变更。同一个 AI 的第二次审查不会被当作独立验证。

## 灵感来源

本 Skill 来自作者自己的思考，也受到以下文章启发：

- Lars Faye：[AI Coding will Prevent Expertise](https://larsfaye.com/articles/ai-coding-will-prevent-expertise)
- Aaron Gray：[AI and Chauffeur Knowledge](https://www.aaron-gray.com/ai-and-chauffeur-knowledge/)

这两篇文章启发了问题框架；Skill 的模式、证据模型、权限边界和工作流是独立设计。

## 许可证

[MIT](../../LICENSE)

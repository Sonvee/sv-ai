# sove-skills

我的个人跨平台 Agent Skills 仓库，面向 Codex、Claude Code、GitHub Copilot、Cursor 及其他兼容 `SKILL.md` 的 AI 编程代理。

## 目录结构

```text
skills/
└── sove-skills/
    ├── SKILL.md
    └── agents/
        └── openai.yaml
```

## 新增 Skill

1. 在 `skills/` 下创建小写连字符命名的 Skill 目录，例如 `review-api-design`。
2. 创建 `SKILL.md`，填写 `name`、`description` 和正文。
3. 如需 Codex/OpenAI UI 集成，添加 `agents/openai.yaml`；其他代理可以忽略该可选目录。
4. 仅在确有需要时添加 `scripts/`、`references/` 或 `assets/`。

每个 Skill 最少需要一个包含 `name` 和 `description` YAML frontmatter 的 `SKILL.md`。

## 常驻规则 Skill

`skills/sove-skills` 保存与厂商、模型和客户端无关的个人硬性规则。核心兼容层只有标准的 `SKILL.md`，不会依赖某个代理的专用工具或提示词格式。

`agents/openai.yaml` 只是 Codex/OpenAI 的可选增强配置，不会改变 `SKILL.md` 的跨平台性质。

## 常见代理安装位置

将完整的 `skills/sove-skills` 目录复制或链接到目标代理支持的位置：

| 代理 | 项目级位置 | 用户级位置 | 常驻指令入口 |
| --- | --- | --- | --- |
| Codex | `.agents/skills/sove-skills` | `~/.agents/skills/sove-skills` | `AGENTS.md` |
| Claude Code | `.claude/skills/sove-skills` | `~/.claude/skills/sove-skills` | `CLAUDE.md` |
| GitHub Copilot | `.github/skills/sove-skills` | 取决于 Copilot 客户端 | `.github/copilot-instructions.md` |
| Cursor | `.cursor/skills/sove-skills` 或 `.agents/skills/sove-skills` | `~/.cursor/skills/sove-skills` | Cursor Rules 或 `AGENTS.md` |

其他支持 Agent Skills 开放格式的工具，只需把该目录放进其 Skill 搜索路径。若工具按需加载 Skill，而你希望规则始终生效，还应在该工具的项目级持久指令文件中明确要求每个任务先读取 `sove-skills/SKILL.md`。

## 本仓库的常驻入口

本仓库已提供以下桥接文件，它们都指向同一份 `skills/sove-skills/SKILL.md`，避免为不同代理维护多份规则：

- `AGENTS.md`：Codex、Cursor 及其他识别该约定的代理。
- `CLAUDE.md`：Claude Code。
- `.github/copilot-instructions.md`：GitHub Copilot。

# sove-skills

`sove-skills` 是一套面向 AI 编程协作的常驻规则与行为指南，适用于 Codex、Claude Code、Cursor 及其他兼容 Agent Skills `SKILL.md` 格式的工具。

它用于统一 AI 在需求理解、代码修改、文档编写、Git 操作、验证方式和服务管理等方面的行为，减少静默假设、过度设计、无关重构和不可验证的实现。

## 主要内容

### Rules

硬性规则，覆盖：

- 中文开发者协作与 UTF-8 编码；
- 延续项目结构、优先复用现有实现和成熟依赖；
- 模块化、文件职责与英文文件名规范；
- 禁止 AI 自动执行 `git commit` 和 `git push`；
- 控制文档规模和代码示例数量；
- 仅使用 Inline Execution，禁止 Subagent 和 Git worktree；
- 测试与验证由开发者手动执行；
- 未经允许不得操作服务生命周期；
- Plan 模式只提供建议验证点，不执行验证。

### Guidelines

行为指南，要求 AI：

- 编码前明确重要假设、可选方案和推荐理由；
- 优先采用满足需求的最小完整方案；
- 只修改与当前需求直接相关的内容；
- 将任务转换为具体、可观察、可由开发者验证的成功标准。

完整规范见 [`skills/sove-skills/SKILL.md`](skills/sove-skills/SKILL.md)。

## 安装

使用 skills CLI 全局安装：

```bash
npx skills add Sonvee/sv-ai --skill sove-skills -g
```

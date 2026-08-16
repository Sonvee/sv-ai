# sv-ai

`sv-ai` 是一组面向 AI 编程协作的个人 Agent Skills，适用于 Codex、Claude Code、Cursor 及其他兼容 `SKILL.md` 格式的工具。

## Skills

### sove-skills

通用协作规则与行为指南，用于约束 AI 的需求理解、代码修改、文档编写、Git 操作、验证方式和服务管理，并强调简单实现、聚焦修改和可验证目标。

完整规范见 [`skills/sove-skills/SKILL.md`](skills/sove-skills/SKILL.md)。

```bash
npx skills add Sonvee/sv-ai --skill sove-skills -g
```

### sove-coding-style

个人编码风格约束，按技术栈拆分并按需加载，目前包含 Vue、前端 UI、JavaScript 和 TypeScript 编程风格。

完整规范见 [`skills/sove-coding-style/SKILL.md`](skills/sove-coding-style/SKILL.md)。

```bash
npx skills add Sonvee/sv-ai --skill sove-coding-style -g
```

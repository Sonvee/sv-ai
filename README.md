# sv-ai

`sv-ai` 是一组面向 AI 编程协作的个人 Agent Skills，适用于 Codex、Claude Code 及其他兼容 `SKILL.md` 格式的工具。

## 仓库集成

本仓库通过 `AGENTS.md` 和 `CLAUDE.md` 引导不同 Agent 工具加载 `skills/sove-skills/SKILL.md`。完整且权威的行为规范始终以该 Skill 文件为准，入口文件不重复维护具体规则。

## 安装全部 Skills

```bash
npx skills add Sonvee/sv-ai -g
```

## Skills

### sove-skills

强制启用的 AI 编程协作基础规范，涵盖需求理解、最小化代码修改、文档与 Git 操作、服务生命周期、精准测试与 TDD、测试失败止损，以及 Inline Execution 和 Subagent 的安全执行约束。

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

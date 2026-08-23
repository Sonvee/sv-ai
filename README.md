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

### sove-blog-writer

按 Sove 个人写作风格规划、撰写和修改中文技术博客。该 Skill 不追求把相关知识写得大而全，而是先明确文章定位、目标读者、内容边界和重点，再围绕读者最需要掌握的主线决定哪些内容详写、略写或删除。

开始写正文前，Skill 会先整理需求并输出文章简报，等待用户确认后再动笔。成文时会根据文章类型和读者基础调整结构与措辞，并确保整篇博客只有一个一级标题。

该 Skill 只能由用户显式指定触发，不会自动调用：

```text
$sove-blog-writer
```

完整规范见 [`skills/sove-blog-writer/SKILL.md`](skills/sove-blog-writer/SKILL.md)。写作风格基线保存在 Skill 内部，不依赖外部博客文章的固定链接。

```bash
npx skills add Sonvee/sv-ai --skill sove-blog-writer -g
```

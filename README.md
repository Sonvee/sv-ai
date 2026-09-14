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

### code-with-docs

文档优先的开发协作流程，用于在正式编程前完成需求对齐、产品需求文档（PRD）和开发计划。该 Skill 会围绕目标、范围、交互、数据、验收标准、技术选型和代码复用策略进行逐项确认，避免 AI 带着关键疑问进入实现阶段。

该 Skill **只能由用户显式指定触发**，不会自动调用：

```text
$code-with-docs
```

使用流程如下：

1. 检查项目上下文和已有文档；
2. 通过一次一个问题的方式完成需求确认，并将每个确认结论增量写入 `docs/prd/`；
3. 基于已确认的 PRD 检查现有代码和依赖，完成技术选型、复用策略和实施设计；
4. 将开发计划写入 `docs/plans/`，并明确改动边界、实施步骤和验证方式；
5. 文档前置工作完成后通知用户已就绪，等待后续明确的开发授权，未获得授权前不会修改业务代码。

需求文档和计划文档支持按主题拆分，并使用带前置序号的小写英文短横线命名，例如 `01-user-auth.md`、`02-order-flow-01.md`。前置序号按对应目录中的最大序号递增，PRD 与 plans 分别独立编号。

完整规范见 [`skills/code-with-docs/SKILL.md`](skills/code-with-docs/SKILL.md)。

```bash
npx skills add Sonvee/sv-ai --skill code-with-docs -g
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

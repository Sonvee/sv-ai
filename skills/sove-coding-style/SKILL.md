---
name: sove-coding-style
description: MUST use for Vue, frontend UI, JavaScript, or TypeScript implementation, review, debugging, and refactoring. Load every applicable coding-style reference before action.
---

# Sove Coding Style

Apply the developer's personal coding-style requirements to relevant implementation, review, debugging, and refactoring tasks.

This skill defines mandatory personal style requirements. It MUST be used alongside `sove-skills`, repository instructions, and all applicable framework or language skills. It does not replace technical correctness or framework guidance. These explicit personal requirements override general project style preferences when both can be applied safely; higher-priority instructions still take precedence.

## Reference Loading

Read only the references relevant to the current task, but load every reference that applies:

- **Vue**: Read [references/vue.md](references/vue.md).
- **Frontend UI**: Read [references/frontend-ui.md](references/frontend-ui.md).
- **JavaScript**: Read [references/javascript.md](references/javascript.md).
- **TypeScript**: Read [references/typescript.md](references/typescript.md).

A task can require multiple references. For example, a Vue component written in TypeScript with visual UI work requires the Vue, TypeScript, and frontend UI references.

## Application Rules

1. Load the applicable references before planning, reviewing, or changing related code.
2. Apply all relevant style requirements together rather than selecting only convenient rules.
3. Apply these requirements to new and modified code. Do not reformat or refactor unaffected existing code solely to make it conform.
4. When a reference does not define the required style, do not invent a personal preference. Follow the existing project conventions and applicable specialized skills.
5. If requirements conflict, follow the higher-priority instruction hierarchy. Among requirements at the same priority, prefer the more specific technology rule over the general rule and the explicit rule in this skill over an inferred convention.
6. Keep technology-specific details in their reference files. Do not expand `SKILL.md` with Vue, UI, JavaScript, or TypeScript style rules.
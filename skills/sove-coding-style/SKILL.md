---
name: sove-coding-style
description: Personal coding-style rules for Vue, frontend UI, JavaScript, and TypeScript. Use whenever writing, reviewing, debugging, or refactoring related code; load all applicable reference files before making changes.
---

# Sove Coding Style

Apply the developer's personal coding-style requirements to relevant implementation, review, debugging, and refactoring tasks.

This skill defines style preferences. It MUST be used alongside `sove-skills`, repository instructions, and all applicable framework or language skills. It does not replace technical correctness, framework guidance, or project-specific conventions.

## Reference Loading

Read only the references relevant to the current task, but load every reference that applies:

- **Vue**: Read [references/vue.md](references/vue.md).
- **Frontend UI**: Read [references/frontend-ui.md](references/frontend-ui.md).
- **JavaScript**: Read [references/javascript.md](references/javascript.md).
- **TypeScript**: Read [references/typescript.md](references/typescript.md).

A task can require multiple references. For example, a Vue component written in TypeScript with visual UI work requires the Vue, TypeScript, and frontend UI references.

## Application Rules

1. Load the applicable references before planning or changing related code.
2. Apply all relevant style requirements together rather than selecting only convenient rules.
3. When a reference is empty or does not define the required style, do not invent a personal preference. Follow the existing project conventions and applicable specialized skills.
4. If style requirements conflict, follow the higher-priority instruction hierarchy. When requirements have equal priority, prefer the more specific technology reference over the more general reference.
5. Keep technology-specific details in their reference files. Do not expand `SKILL.md` with Vue, UI, JavaScript, or TypeScript style rules.
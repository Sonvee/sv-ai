---
name: sove-skills
description: Always-on mandatory rules for Chinese-developer collaboration. MUST trigger for EVERY task and user request before any planning or action, remain active until completion, and apply alongside all other skills. Enforces language, UTF-8, reuse, modularity, naming, Git, documentation, inline-only execution, developer-run verification, service lifecycle, and Plan-mode constraints.
---

# Sove Skills - Universal AI Collaboration Rules

Apply these rules regardless of the current agent, model, IDE, CLI, or hosting platform. Treat every rule as mandatory unless it conflicts with a higher-priority platform, security, system, developer, user, or repository instruction.

Normative keywords such as MUST, MUST NOT, SHOULD, and SHOULD NOT are intentional.

## Mandatory Activation

1. This is an always-on skill. It MUST trigger for every new task and every user request, without exception.
2. Load this skill before planning, reasoning, inspecting files, searching, editing, running commands, or writing a response.
3. Keep every rule active throughout the full task, including follow-up requests, revisions, Plan mode, implementation, and the final response.
4. Re-read this skill whenever work resumes after interruption, context compaction, handoff, or a long-running operation.
5. Never omit or replace this skill because another specialized skill is active. Apply both.

## Core Operating Principles

1. Identify and use all other applicable specialized skills. This skill does not replace domain-specific guidance.
2. Inspect only the context needed to understand the current implementation, project conventions, and impact. Do not guess facts that can be established from local files, available tools, or authoritative sources.
3. Make the smallest coherent change that fully satisfies the request. Avoid unrelated refactors, formatting churn, generated artifacts, and unrequested features.
4. Do not overwrite, revert, or rewrite unrelated work created by the user or other developers. Stop the affected change and report any conflict that cannot be handled safely.
5. Follow the active instruction hierarchy and every applicable repository instruction file, including `AGENTS.md`, `CLAUDE.md`, and `.github/copilot-instructions.md`.
6. Use only capabilities and tools that are actually available in the current environment. Never fabricate actions, outputs, verification results, or tool access.

## 1. Language Rules

- Collaboration is intended for a Chinese-speaking developer. Explanations, summaries, plans, documentation, and code comments SHOULD use Chinese by default.
- Preserve established English technical terms, API names, protocol fields, library and framework names, commands, code identifiers, original error messages, and any English content explicitly requested by the user.
- Do not translate established technical terms merely to make all content Chinese when translation would reduce precision or introduce ambiguity.
- These language requirements apply to agent output and project content. They do not require this `SKILL.md` itself to be written in Chinese.

## 2. Encoding Rules

- New text files SHOULD use UTF-8.
- Before editing an existing file, identify and preserve its valid encoding, BOM, and line-ending style. Convert it to UTF-8 only when the conversion is safe and does not corrupt content.
- MUST NOT write mojibake, incorrectly transcoded text, unexplained replacement characters, or corrupted content.
- When an encoding problem is suspected, stop editing that file and determine the correct encoding before proceeding. Do not overwrite it blindly.

## 3. Code Reuse Rules

- Prefer the project's existing structure, framework conventions, toolchain, shared components, module organization, and code style.
- Avoid reinventing existing functionality.
- Before creating a utility function, wrapper, helper, or reusable abstraction, MUST first evaluate existing project implementations, installed dependencies, and suitable mainstream open-source solutions. MUST NOT handwrite such functionality without completing this evaluation.
- Before adopting an existing or open-source solution, evaluate maintenance status, compatibility, security, license, bundle or runtime cost, and integration complexity. Do not add a dependency blindly for trivial functionality.
- Organize code into focused, reusable components and modules. Extract only genuinely stable shared behavior; avoid unnecessary abstraction and over-engineering.

## 4. File Splitting Rules

- Keep each file focused on a clear responsibility with well-defined boundaries.
- Proactively split a file when it becomes excessively large, mixes independent concerns, or continues to grow without a clear boundary.
- MUST NOT allow a single source file to grow to thousands or tens of thousands of lines.
- Split by domain, responsibility, component, or feature while keeping public interfaces clear. Avoid circular dependencies and meaningless fragmentation.

## 5. Naming Rules

- File and directory names MUST NOT contain Chinese characters, to avoid cross-platform, toolchain, archive, deployment, and version-control compatibility issues.
- Follow the project's existing naming convention. When no convention exists, use clear English names and the casing style customary for the current ecosystem, such as kebab-case or snake_case.

## 6. Git Rules

- The AI MUST NOT execute `git commit`, `git push`, or any equivalent commit or upload operation.
- Only the developer may manually commit and push changes.
- Unless explicitly requested by the user, the AI MUST NOT rewrite Git history, create tags, or modify remote branches.

## 7. Documentation Rules

- Design and development documentation MUST NOT contain large amounts of business code examples.
- Include only the smallest code snippet necessary to explain a core design or critical usage pattern. Do not copy large blocks of production code into documentation as filler.
- Split long documentation by topic and provide clear navigation. MUST NOT create a single excessively long document containing multiple independent subjects.

## 8. Task Execution Rules

- Use Inline Execution only.
- MUST NOT use a Subagent-Driven workflow and MUST NOT create, invoke, or delegate work to subagents.
- MUST NOT create or use a Git worktree. Perform all permitted work in the current working tree.

## 9. Testing and Verification Rules

- The AI MUST NOT create test files, test cases, test data, test fixtures, or test scripts.
- All testing and verification MUST be performed manually by the developer.
- The AI MUST NOT run tests, builds, type checks, linters, format checks, end-to-end tests, validation scripts, or any other verification command.
- After completing code or configuration changes, provide manual verification guidance containing the recommended verification points, prerequisites, commands, and steps the developer should execute.
- Until the developer reports the verification result, do not claim that the change has passed tests or validation. State only that the requested modifications are complete and awaiting developer verification.

## 10. Service Lifecycle Rules

- Without explicit user permission, the AI MUST NOT start, restart, stop, terminate, or relaunch any development, test, database, container, or background service.
- If a required service is not running, tell the developer which command to run manually. Do not start it on the developer's behalf.
- If the service is already running, do not start a duplicate or redundant instance.
- Do not assume that a service can be operated safely when its current state is unknown.

## 11. Plan Mode Rules

- In Plan mode, omit execution of tests and verification. List only recommended verification points and the commands the developer should run manually.
- A plan MUST NOT instruct the AI to create test files or test cases, or to execute tests or verification commands.
- The developer is solely responsible for performing the actual tests and verification.

## Conflict Handling

- Follow higher-priority instructions from the active platform and instruction hierarchy.
- If another skill conflicts with this skill, follow this skill's mandatory constraints unless doing so would violate a higher-priority instruction.
- If a rule cannot be followed, do not skip it silently. Explain the conflict or limitation and choose the safest compliant approach.

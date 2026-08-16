# TypeScript Coding Style

Apply these requirements whenever writing, reviewing, debugging, or refactoring TypeScript code.

Normative keywords such as MUST, MUST NOT, SHOULD, and SHOULD NOT are intentional.

## TSDoc Documentation

- TypeScript code MUST follow standard TSDoc or JSDoc-compatible documentation conventions supported by the project toolchain.
- Add documentation comments to exported functions, classes, objects, types, interfaces, complex utility methods, and public APIs when their contracts are not self-explanatory.
- Use a complete documentation block when code has complex parameters, return values, exceptions, callbacks, generic type parameters, side effects, or business constraints.
- Use appropriate standard tags such as `@param`, `@returns`, `@throws`, `@typeParam`, and `@example` only when they add meaningful contract information.
- Document business intent, caller obligations, boundary conditions, side effects, and non-obvious design decisions.
- MUST NOT restate TypeScript type annotations or repeat obvious implementation steps.
- Keep documentation synchronized with the implementation and type contract whenever either changes.

## Utility Reuse

Before implementing a utility function or reusable type utility, evaluate reusable solutions in this order:

1. Native JavaScript, TypeScript, or runtime APIs and built-in utility types.
2. APIs and types provided by the active framework.
3. Existing project utilities, shared types, and local wrappers.
4. Suitable methods and type definitions from dependencies already installed by the project.
5. A maintained mainstream library when adding it materially reduces complexity or risk.
6. A small, scoped handwritten implementation only when it is simpler and clearer than introducing a dependency.

Rules:

- Prefer an existing reliable utility, standard API, framework API, or built-in utility type over a custom implementation.
- MUST NOT duplicate functionality or reusable types that the project or an installed dependency already provides.
- Before importing a utility-library method or type, confirm that the dependency or local wrapper already exists in the project.
- When the appropriate reusable solution requires a dependency that is not installed, recommend the dependency and ask the developer to install it instead of silently writing a replacement implementation.
- Recommend a new dependency only after confirming that it meaningfully reduces implementation complexity, maintenance cost, or correctness risk.
- Do not add a dependency for trivial functionality when a small local implementation is more direct, type-safe, and easier to maintain.
- A handwritten implementation is allowed when it is narrower, clearer, type-safe, and lower-cost than adding a dependency. Keep it local to the actual use case and MUST NOT let equivalent copies accumulate across the project.
- Follow the project package manager and existing dependency-management conventions when providing installation guidance.
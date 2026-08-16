# JavaScript Coding Style

Apply these requirements whenever writing, reviewing, debugging, or refactoring JavaScript code.

Normative keywords such as MUST, MUST NOT, SHOULD, and SHOULD NOT are intentional.

## JSDoc Documentation

- JavaScript code MUST follow standard JSDoc conventions.
- Add JSDoc to exported functions, classes, objects, complex utility methods, and public APIs.
- Use a complete JSDoc block when code has complex parameters, return values, exceptions, callbacks, generic templates, or business constraints.
- Use appropriate standard tags such as `@param`, `@returns`, `@throws`, `@callback`, and `@template` to describe the contract precisely.
- Document business intent, caller obligations, boundary conditions, side effects, and non-obvious design decisions.
- MUST NOT repeat obvious implementation steps or restate information that is already clear from the code.
- Keep JSDoc synchronized with the implementation whenever the documented contract changes.

## Utility Reuse

Before implementing a utility function, evaluate reusable solutions in this order:

1. Native JavaScript or runtime APIs.
2. APIs provided by the active framework.
3. Existing project utilities and local wrappers.
4. Suitable methods from dependencies already installed by the project.
5. A maintained mainstream library when adding it materially reduces complexity or risk.
6. A small, scoped handwritten implementation only when it is simpler and clearer than introducing a dependency.

Rules:

- Prefer an existing reliable utility, standard API, or framework API over a custom implementation.
- MUST NOT duplicate functionality that the project or an installed dependency already provides.
- Before importing a utility-library method, confirm that the dependency or local wrapper already exists in the project.
- When the appropriate reusable solution requires a dependency that is not installed, recommend the dependency and ask the developer to install it instead of silently writing a replacement implementation.
- Recommend a new dependency only after confirming that it meaningfully reduces implementation complexity, maintenance cost, or correctness risk.
- Do not add a dependency for trivial functionality when a small local implementation is more direct and easier to maintain.
- A handwritten implementation is allowed when it is narrower, clearer, and lower-cost than adding a dependency. Keep it local to the actual use case and MUST NOT let equivalent copies accumulate across the project.
- Follow the project package manager and existing dependency-management conventions when providing installation guidance.
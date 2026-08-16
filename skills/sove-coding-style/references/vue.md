# Vue Coding Style

Apply these requirements whenever creating, editing, reviewing, or refactoring Vue Single-File Components and Vue page structures.

Normative keywords such as MUST, MUST NOT, and SHOULD are intentional.

## Vue SFC Template

Vue page and component SFCs MUST use the following block order and declarations:

```vue
<template></template>

<script lang="ts" setup></script>

<style lang="scss" scoped></style>
```

- Keep the order `template` -> `script` -> `style`.
- MUST NOT change the layout to script-first or any other block order.
- Keep `lang="ts"` and `setup` on the `script` block.
- Keep `lang="scss"` and `scoped` on the `style` block.

## Page Structure

When creating a new Vue page, use a dedicated page directory:

```text
src/views/<page-name>/index.vue
```

Rules:

- `<page-name>` MUST use kebab-case.
- MUST NOT create a page as a direct single file under `src/views`, such as `src/views/home.vue`.
- If the developer provides only a page name, infer the kebab-case directory name and create the required directory structure automatically.
- Keep page-specific files in the same page directory, such as `index.ts`, `types.ts`, `style.scss`, and `__tests__/`.

Examples:

```text
Home -> src/views/home/index.vue
AboutMe -> src/views/about-me/index.vue
```

## Global Component Structure

When creating a new global Vue component, use a dedicated component directory:

```text
src/components/<ComponentName>/<ComponentName>.vue
```

Rules:

- `<ComponentName>` MUST use PascalCase.
- MUST NOT create a global component as a direct single file under `src/components`, such as `src/components/HelloWorld.vue`.
- If the developer provides only a component name, infer the PascalCase name and create the required directory structure automatically.
- Keep component-specific files in the same component directory, such as `index.ts`, `types.ts`, `style.scss`, and `__tests__/`.

Example:

```text
HelloWorld -> src/components/HelloWorld/HelloWorld.vue
```

## Page-Specific Components

When a component is used only by one page, place it under that page's local `components` directory:

```text
src/views/<page-name>/components/<ComponentName>.vue
```

- MUST NOT promote a page-specific business component to the global `src/components` directory.
- Move a component to the global directory only when it is genuinely shared across pages and the developer's request requires that scope.

## Testing Constraint

The `__tests__/` examples above define only the required location for existing or developer-created page and component tests. They do not authorize the AI to create test files, test cases, fixtures, or test data. Continue to follow the Testing and Verification Rules from `sove-skills`.
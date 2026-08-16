# Frontend UI Coding Style

Apply these requirements whenever creating, editing, reviewing, or refactoring frontend UI, visual components, styles, icons, or client-side state used by the UI.

Normative keywords such as MUST, MUST NOT, SHOULD, and SHOULD NOT are intentional.

## Icon Selection Priority

When the frontend requires icons, icon fonts, or an icon set, evaluate options in this order:

1. Existing project iconfont assets.
2. Icons provided by the installed UI component library, such as Element Plus Icons.
3. Icon integrations associated with an installed utility-first CSS solution, such as Tailwind CSS or UnoCSS.

Rules:

- First inspect the project for existing iconfont resources and reuse a suitable existing iconfont icon whenever possible.
- If the existing iconfont cannot satisfy the requirement, use a suitable icon from the project's installed UI component library.
- Use a Tailwind CSS, UnoCSS, or similar icon integration only when the corresponding solution and icon capability are already installed and configured in the project.
- MUST NOT install or introduce multiple icon systems for an ordinary icon requirement.
- Follow the project's established icon rendering, sizing, coloring, naming, and accessibility conventions.

## State Management and Persistence

- In a Vue project using Pinia, prefer `pinia-plugin-persistedstate` when store persistence is required.
- Use `localStorage` as the default local persistence target unless the requirement or existing project architecture specifies another storage mechanism.
- MUST NOT persist sensitive information, short-lived transient state, or data that can be reliably restored from the server without a clear requirement.
- Split stores by business domain and responsibility. MUST NOT allow a single store to accumulate unrelated state and behavior.
- Persist only the minimum fields required by the feature rather than the entire store by default.
- Before using `pinia-plugin-persistedstate`, confirm that it is already installed. If it is required but missing, recommend the dependency and ask the developer to install it instead of silently introducing a custom persistence implementation.

## Styling Priority

When choosing how to implement styles, use the following priority only among styling solutions already available in the project:

1. Tailwind CSS.
2. UnoCSS.
3. SCSS.
4. CSS.

Rules:

- Existing project conventions take precedence. Continue using the established styling solution, component-library theme system, tokens, utilities, and naming conventions.
- Place component-private styles close to the component by default.
- MUST NOT introduce a new styling system for a local or isolated styling requirement.
- Do not mix multiple styling approaches in the same component without a concrete need established by the existing codebase or requirement.
- Reuse existing design tokens, utility presets, CSS variables, mixins, and shared style abstractions before defining equivalents.

## Component Library Usage

- When the project already includes a UI component library, prefer its foundational components and established interaction patterns over custom equivalents.
- Before using a component, icon, composable, or theme API, confirm that it belongs to the installed library and is available in the project's current setup.
- Business components MUST expose clear and intentional `props`, events, and slots.
- MUST NOT copy large amounts of similar UI markup across the project.
- Extract a business component when a UI structure is stable, meaningfully repeated, and represents a clear business or interaction responsibility.
- Do not create an abstraction for a one-off visual fragment solely to make the code appear reusable.
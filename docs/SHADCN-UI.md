# shadcn/UI Component Standards

## Required UI System

- Use shadcn/ui components for every UI element in this application.
- Do not create custom UI components or duplicate shadcn primitives with hand-built equivalents.
- Add missing primitives with the project's shadcn CLI and configuration in `components.json`.
- Place generated primitives in `components/ui/` and import them through `@/components/ui/...`.
- Do not use plain HTML form controls or custom buttons when a shadcn component is available.

## Components and Composition

- Reuse shadcn components before adding any new component.
- Compose application features from shadcn primitives rather than extending the DOM with bespoke visual widgets.
- Extend a generated shadcn component through its existing variants or `className` API before considering another abstraction.
- Keep application-specific composition under `app/` or `components/` only when it combines existing shadcn components.
- Do not fork or substantially restyle shadcn primitives outside the generated component files.

## Styling

- Use Tailwind CSS classes and the theme variables in `app/globals.css`.
- Preserve shadcn variants, CSS variables, focus states, dark mode, and Base UI behavior.
- Use `cn` for conditional class composition.
- Do not introduce separate UI libraries or custom design systems.
- Do not replace shadcn components with native `<button>`, `<input>`, `<select>`, `<dialog>`, or equivalent controls unless an existing shadcn primitive cannot represent the element.

## Accessibility

- Preserve shadcn keyboard navigation, focus management, labels, and ARIA behavior.
- Use semantic text, icon labels, or shadcn-supported accessibility props for icon-only controls.
- Do not remove focus rings or disabled states.
- Verify responsive layouts and dark-mode appearance after UI changes.


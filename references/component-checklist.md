# Vue 3 Reusable Component Checklist

## API contract
- Keep `props` minimal and purpose-driven.
- Use explicit TypeScript interfaces/types.
- Provide stable defaults and avoid surprising implicit behavior.
- Keep `emits` names action-oriented (e.g., `submit`, `change`, `update:modelValue`).
- Document each slot's purpose and payload shape.
- If using `defineExpose`, expose only small, stable, typed methods.

## Parent integration DX (must pass)
- Parent can complete basic integration with very low boilerplate.
- Component supports clear controlled/uncontrolled usage when applicable.
- `v-model` contract is consistent (`modelValue` + `update:modelValue`) when editable state exists.
- Event payloads are explicit and easy for parent to consume.
- Public API naming is consistent with sibling components.

## Composition API quality
- Use `<script setup lang="ts">` where possible.
- Avoid unnecessary `watch`; prefer `computed` when derivation is pure.
- Avoid mutating props directly.
- Keep side effects inside lifecycle hooks or explicit handlers.

## Reusability
- Separate domain-specific logic from generic rendering logic.
- Expose extension points via slots and CSS variables.
- Avoid leaking parent state assumptions.

## Accessibility
- Ensure all interactive elements are keyboard reachable.
- Provide meaningful accessible names.
- Use native HTML semantics first, ARIA second.
- Validate disabled/loading states with proper attributes.

## Maintainability
- Keep file focused on a single component responsibility.
- Extract repeated logic into composables.
- Keep naming consistent and intention-revealing.
- Prefer readable code over clever abstractions.

## Documentation and examples (must pass)
- Provide API summary for `props` / `emits` / `slots` / `expose`.
- Provide parent integration notes (how to wire state and events).
- Provide at least one minimal usage example.
- Provide at least one realistic/advanced usage example.
- Ensure examples match actual component behavior and types.


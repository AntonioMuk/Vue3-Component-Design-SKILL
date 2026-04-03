# Vue 3 Component Checklist

Use this checklist before final delivery.

## 1) API contract
- `props` are minimal, explicit, and purpose-driven.
- Prop types and defaults are clear.
- Editable state uses `modelValue` + `update:modelValue` when applicable.
- `emits` names are action-oriented and payloads are typed.
- Slots have defined purpose, slot props, and fallback behavior.
- `defineExpose` is used only when necessary and exposes a small typed surface.

## 2) Parent integration
- Basic usage is low-boilerplate.
- No hidden required props or hidden ordering assumptions.
- Default behavior is useful without advanced configuration.
- Parent can control important states when relevant.
- API names match sibling component conventions.

## 3) Implementation readability
- Component has one clear responsibility.
- `<script setup lang="ts">` is used where appropriate.
- Template is shallow and readable.
- Complex derivation is moved to `computed` or helpers.
- Side effects are isolated to clear handlers or lifecycle hooks.
- Prop mutation is avoided.

## 4) Reusability
- Generic UI logic is not tightly coupled to one business case.
- Shared logic is extracted only when real reuse exists.
- Extension points are provided through slots or style hooks.
- Public payload shapes are stable and easy to consume.

## 5) Accessibility baseline
- Interactive elements are keyboard reachable.
- Accessible names are meaningful.
- Native semantics are preferred before ARIA.
- Disabled/loading states are reflected correctly.

## 6) Delivery quality
- API summary matches the actual code.
- Parent integration notes match the real usage pattern.
- Minimal and realistic examples both run without hidden dependencies.
- Boundaries and assumptions are stated clearly.

## 7) Red flags
- Too many props for a simple component.
- Template contains business logic or heavy branching.
- Component mutates parent-owned state directly.
- `defineExpose` is used as a shortcut for poor API design.
- Multiple unrelated responsibilities live in one file.

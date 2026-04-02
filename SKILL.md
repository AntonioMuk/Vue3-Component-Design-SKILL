---
name: vue3-component-dev
description: This skill should be used when designing, implementing, refactoring, or reviewing reusable Vue 3 components with Composition API, TypeScript, slots/emits contracts, accessibility, maintainable styling, and parent-friendly integration APIs.
---

# Vue 3 Component Development Skill

## Purpose

Deliver reusable Vue 3 components that are easy for parent components to integrate, easy for teams to maintain, and easy to document and demonstrate.

## When to use

Use this skill when tasks involve one or more of the following:
- Design a new Vue 3 component API.
- Build or refactor reusable UI/business components.
- Standardize `props`, `emits`, `slots`, and `defineExpose` contracts.
- Improve component readability, maintainability, and testability.
- Add accessibility support or strengthen TypeScript typing.
- Produce component usage documentation and runnable examples.

## Non-negotiable design principles

1. Parent integration first.
   - Every component must provide a parent-friendly API with minimal boilerplate.
   - Prefer consistent conventions: `v-model` / `update:modelValue`, action-style emits (`submit`, `cancel`), and clear prop names.
   - If imperative control is needed, expose a small typed surface via `defineExpose`.

2. Contract before implementation.
   - Define `Props` with explicit TypeScript types and safe defaults.
   - Define `Emits` with typed payloads and trigger semantics.
   - Define `Slots` (name, purpose, payload shape, fallback behavior).
   - Keep API minimal and stable; remove speculative options.

3. Documentation and examples are mandatory deliverables.
   - For each component, provide usage notes explaining parent integration patterns.
   - Provide at least one minimal example and one realistic example.
   - Examples must show how parent components pass data, handle events, and consume exposed methods when applicable.

## Core workflow

1. Clarify component goal and usage context.
   - Define user-visible behavior first.
   - Identify whether component is presentational, container, or composite.
   - Define the expected parent-child interaction mode (controlled, uncontrolled, hybrid).

2. Design component contract before coding.
   - Draft public API (`props`, `emits`, `slots`, optional exposed methods).
   - Validate the API from parent perspective: "Can parent integrate this in <= 5 lines for basic use?"
   - Add naming consistency checks against existing project conventions.

3. Implement with Composition API conventions.
   - Prefer `<script setup lang="ts">`.
   - Keep reactive state minimal and colocated with behavior.
   - Extract reusable logic into composables when behavior is shared across components.
   - Avoid mixing unrelated concerns in one file.

4. Build reusable template structure.
   - Keep template semantic and shallow.
   - Use clear sectioning (`header`, `main`, `footer`, etc.) where meaningful.
   - Avoid deep nesting and duplicated markup.

5. Enforce styling boundaries.
   - Prefer scoped styles or a clear BEM-like naming scheme.
   - Expose style extension points through classes/CSS variables instead of hardcoded overrides.
   - Preserve predictable theming behavior.

6. Add accessibility baseline by default.
   - Ensure keyboard operability for interactive elements.
   - Add proper labels/roles/states (`aria-*`) where native semantics are insufficient.
   - Preserve focus visibility and logical tab order.

7. Verify parent DX and reusability.
   - Validate typical usage, edge cases, and empty/error states.
   - Ensure emitted events and slot contracts match definitions.
   - Confirm component can be used with minimal parent boilerplate.
   - Confirm docs and examples reflect real API behavior.

## Output requirements

When delivering or modifying a component, include:
- A concise API summary (`props`, `emits`, `slots`, `expose` if used).
- Parent integration guide (basic wiring, common patterns, pitfalls).
- A minimal example and an advanced/realistic example.
- Any assumptions made for missing product details.
- Clear component boundaries (what is and is not handled).

## Reference

Load and follow these files before finalizing:
- `references/component-checklist.md`
- `references/parent-api-guidelines.md`
- `references/component-doc-example-template.md`


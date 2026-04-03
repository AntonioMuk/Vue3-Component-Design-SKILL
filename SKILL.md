---
name: vue3-component-dev
description: This skill should be used when designing, implementing, refactoring, or reviewing reusable Vue 3 components with standardized API contracts, readable code structure, and parent-friendly integration patterns.
---

# Vue 3 Component Development Skill

## Purpose

Build or refactor Vue 3 components with standardized public APIs, readable implementation, and reusable integration patterns.

## When to use

Use this skill when work involves:
- Designing a new Vue 3 component.
- Refactoring or reviewing an existing component.
- Standardizing `props`, `emits`, `slots`, or `defineExpose`.
- Improving readability, reusability, or parent integration.
- Delivering usage notes and runnable examples for a component.

## Operating mode

1. Inspect before editing.
   - Read the target component and its parent usage before changing the public API.
   - Reuse existing project naming, event semantics, and style conventions.
   - Check sibling components before introducing a new pattern.

2. Define the contract before coding.
   - Decide component role: presentational, form, composite, or container.
   - Draft `props`, `emits`, `slots`, and optional `expose` first.
   - Choose controlled, uncontrolled, or hybrid interaction mode.
   - Keep basic usage low-boilerplate and predictable.

3. Implement for readability.
   - Prefer `<script setup lang="ts">`.
   - Keep one clear responsibility per component.
   - Keep templates shallow, semantic, and easy to scan.
   - Move complex template logic into `computed`, helpers, or composables.
   - Prefer readable code over clever abstractions.

4. Implement for reusability.
   - Keep generic rendering separate from domain-specific rules.
   - Extract composables only when logic is truly shared.
   - Provide extension points through slots and style hooks.
   - Avoid hidden parent assumptions.

5. Validate before delivery.
   - Ensure public API names are consistent and minimal.
   - Ensure emitted payloads, slot props, and exposed methods match the implementation.
   - Check empty, loading, disabled, and error states when relevant.
   - Keep docs and examples consistent with real code.

## Standardized API rules

- Define props explicitly; avoid implicit or hidden requirements.
- Prefer `v-model` (`modelValue` + `update:modelValue`) for editable state.
- Use action-style events such as `submit`, `cancel`, `confirm`, `change`.
- Expose only small typed methods through `defineExpose` when declarative API is not enough.
- Keep defaults safe and behavior unsurprising.
- Remove speculative options that do not serve a real use case.

## Readability rules

- Use intention-revealing names.
- Keep related logic colocated.
- Avoid direct prop mutation.
- Avoid unnecessary `watch`; prefer `computed` for pure derivation.
- Avoid deep nesting in both template and script.
- Split components when responsibilities diverge.

## Reusability rules

- Keep the public API stable and easy to learn.
- Make parent integration possible with low boilerplate.
- Keep event payloads explicit and consistent.
- Allow extension through slots before adding more props.
- Expose styling hooks through classes or CSS variables instead of hardcoded overrides.

## Required output

When delivering or modifying a component, include:
- API summary: `props`, `emits`, `slots`, `expose`.
- Component boundary: what it handles and does not handle.
- Parent integration notes: basic wiring and common pitfalls.
- One minimal example and one realistic example.
- Explicit assumptions for missing product details.

## External skill invocation

When component work depends on extracting or migrating an existing visual style, invoke external skill:
- `ui-style-learner`

Use `ui-style-learner` to analyze local HTML/Vue/CSS files or webpage URLs, extract design tokens and layout/style patterns, then apply those findings during component design and implementation.

## References

Load these files as needed:
- `references/component-checklist.md` for pre-delivery verification.
- `references/parent-api-guidelines.md` for public API decisions.
- `references/component-doc-example-template.md` for delivery structure and examples.

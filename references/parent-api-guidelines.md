# Parent-Friendly API Guidelines (Vue 3)

## Goal
Design component APIs that let parent components integrate quickly, safely, and predictably.

## Required conventions

1. Editable state
- Prefer `v-model` contract for editable value:
  - Prop: `modelValue`
  - Emit: `update:modelValue`
- If multiple models are needed, use named model conventions consistently.

2. Action events
- Use action-oriented names: `submit`, `confirm`, `cancel`, `change`.
- Emit payloads with explicit TypeScript shapes.
- Keep event semantics stable (same trigger conditions across versions).

3. Imperative API (`defineExpose`)
- Only expose when declarative API is insufficient.
- Expose minimal methods (e.g., `focus`, `reset`, `validate`).
- Methods must be typed and side effects must be documented.

4. Slot contract
- Define each slot's purpose.
- If slot props exist, document full payload shape.
- Provide fallback behavior when slot not provided.

## Parent DX checklist
- Basic usage in <= 5 lines possible.
- No hidden required props.
- Default behavior is useful without advanced configuration.
- Errors/empty/loading states can be controlled by parent.
- API names align with existing component patterns in the project.

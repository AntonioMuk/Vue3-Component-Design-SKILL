# Parent-Friendly API Guidelines (Vue 3)

Use these rules when deciding a component's public API.

## 1) Choose the interaction model first
- Use controlled mode when parent owns the state.
- Use uncontrolled mode only when internal state is sufficient.
- Use hybrid mode only when there is a real need for both.

## 2) Standard patterns

### Editable state
- Prefer `v-model` for the primary editable value.
- Use `modelValue` as the prop and `update:modelValue` as the emit.
- If multiple models are needed, use named models consistently.

### Action events
- Prefer action-oriented names: `submit`, `confirm`, `cancel`, `change`, `open`, `close`.
- Keep event timing and meaning stable.
- Emit explicit payload shapes.

### Slots
- Add a slot only when the parent needs structural customization.
- Document each slot's purpose.
- Document slot props completely.
- State fallback behavior when the slot is absent.

### Imperative API
- Use `defineExpose` only when declarative API is not enough.
- Expose minimal methods such as `focus`, `reset`, or `validate`.
- Keep methods typed and document side effects.

## 3) API design constraints
- Keep basic usage simple.
- Avoid hidden required combinations of props.
- Avoid boolean-prop explosions; prefer clearer composition patterns.
- Prefer one obvious way to perform the common task.
- Align names with existing project patterns.

## 4) Parent DX checks
- Can the parent complete basic integration in a few lines?
- Can the parent understand events without reading internal code?
- Can the parent predict default behavior without extra configuration?
- Can the parent handle empty/loading/error states when needed?

## 5) Anti-patterns
- Using props for imperative commands.
- Emitting vague events such as `done` or `callback`.
- Exposing too many internal methods.
- Adding props for edge cases that should be solved by slots or composition.

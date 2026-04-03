# Component Delivery Template

Use this template when creating or refactoring a component. Fill it with the real API only. Do not invent unsupported props, events, slots, or methods.

## 1) Component summary
- Name:
- Purpose:
- Boundary (handles / does not handle):

## 2) Public API
### Props
- `propName`: type, default, required, description

### Emits
- `eventName(payload)`: when it fires, payload type, meaning

### Slots
- `slotName`: purpose, slot props, fallback behavior

### Exposed methods (optional)
- `methodName(args)`: return type, side effects, when parent should call it

## 3) Parent integration notes
- Basic wiring steps
- Controlled / uncontrolled / hybrid mode
- Common pitfalls and recommended usage

## 4) Example A (minimal)
```vue
<script setup lang="ts">
import { ref } from 'vue'
import MyComponent from './MyComponent.vue'

const value = ref('')
</script>

<template>
  <MyComponent v-model="value" />
</template>
```

## 5) Example B (realistic)
```vue
<script setup lang="ts">
import { ref } from 'vue'
import MyComponent from './MyComponent.vue'

const value = ref('initial')
const loading = ref(false)

function handleSubmit(payload: { value: string }) {
  loading.value = true
}
</script>

<template>
  <MyComponent
    v-model="value"
    :loading="loading"
    @submit="handleSubmit"
  >
    <template #footer>
      <button type="button">Custom Action</button>
    </template>
  </MyComponent>
</template>
```

## 6) Final verification
- Docs match actual implementation names and types.
- Examples run without hidden dependencies.
- Examples show parent-side state, events, and slot usage clearly.

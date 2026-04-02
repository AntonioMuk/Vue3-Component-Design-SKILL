# Component Documentation + Example Template

Use this template whenever a component is created or refactored.

## 1) Component summary
- Name:
- Purpose:
- Responsibility boundary (handles / does not handle):

## 2) Public API
### Props
- `propName`: type, default, required, description

### Emits
- `eventName(payload)`: trigger timing, payload type, meaning

### Slots
- `slotName`: purpose, slot props, fallback behavior

### Exposed methods (optional)
- `methodName(args)`: return type, side effects, when parent should call

## 3) Parent integration guide
- Basic integration steps
- Controlled/uncontrolled mode explanation (if applicable)
- Common pitfalls and recommended patterns

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
  // async action
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

## 6) Validation before delivery
- Docs match actual implementation types and names.
- Both examples run without hidden dependencies.
- Example shows parent-side state, events, and slot usage clearly.

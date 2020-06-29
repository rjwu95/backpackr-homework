<template>
  <InputForm
    :defaultContent="defaultContent"
    :maxlength="maxlength"
    :disabled="disabled"
    :readonly="readonly"
    :placeholder="placeholder"
  />
</template>

<script>
import InputForm from './InputForm.vue'

export default {
  name: 'ReadonlyInput',
  components: { InputForm },
  props: {
    defaultContent: {
      type: String
    },
    maxlength: {
      type: Number
    },
    disabled: {
      type: Boolean
    },
    readonly: {
      type: Boolean,
      default: true
    },
    placeholder: {
      type: String
    }
  }
}
</script>

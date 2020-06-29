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
  name: 'DisabledInput',
  components: { InputForm },
  props: {
    defaultContent: {
      type: String
    },
    maxlength: {
      type: Number
    },
    disabled: {
      type: Boolean,
      default: true
    },
    readonly: {
      type: Boolean
    },
    placeholder: {
      type: String
    }
  }
}
</script>

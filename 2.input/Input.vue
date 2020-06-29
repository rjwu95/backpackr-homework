<template>
  <InputForm
    :defaultContent="defaultContent"
    :maxlength="maxlength"
    :disabled="disabled"
    :readonly="readonly"
    :placeholder="placeholder"
    @save="$emit('save')"
  />
</template>

<script>
import InputForm from './InputForm.vue'

export default {
  name: 'Input',
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
      type: Boolean
    },
    placeholder: {
      type: String
    }
  }
}
</script>

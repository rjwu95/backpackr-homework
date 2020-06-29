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
      type: String,
      required: false,
      default: ''
    },
    maxlength: {
      type: Number,
      default: 500
    },
    disabled: {
      type: Boolean,
      default: false
    },
    readonly: {
      type: Boolean,
      default: true
    },
    placeholder: {
      type: String,
      default: '내용을 입력해 주세요.'
    }
  }
}
</script>

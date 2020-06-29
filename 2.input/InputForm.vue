<template>
  <div class="container">
    <div class="text-container" :style="{ 'background-color': readonly ? 'yellow' : '', 'border-color': isFocused ? 'skyblue' : 'gray' }">
      <textarea
        v-model="content"
        :placeholder="placeholder"
        :maxlength="maxlength"
        :disabled="disabled"
        :readonly="readonly"
        @focus="isFocused = true"
        @blur="isFocused = false"
      ></textarea>
      <div class="remain-text-number">{{ remainingTextNumber }}</div>
    </div>
    <button v-if="isNewContent" @click="$emit('save', content)">save</button>
  </div>
</template>

<script>
export default {
  name: 'InputForm',
  props: {
    defaultContent: {
      type: String,
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
      default: false
    },
    placeholder: {
      type: String,
      default: '내용을 입력해 주세요.'
    }
  },
  data() {
    return {
      content: this.defaultContent,
      isFocused: false
    }
  },
  computed: {
    isNewContent() {
      return this.content !== this.defaultContent
    },
    remainingTextNumber() {
      return this.maxlength - this.content.length
    }
  },
}
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: row;
  margin-top: 30px
}
.text-container {
  flex: 1;
  border: solid gray;
  display: flex;
  flex-direction: row;
  height: 100px;
  justify-content: space-between;
  padding: 0 15px;
}
textarea {
  border: none;
  resize: none;
  width: 80%
}
textarea:read-only {
  background-color: yellow;
}
textarea:focus {
  outline: none;
}
.remain-text-number {
  align-self: flex-end;
  justify-self: flex-end;
}
button {
  flex: 0.1
}
</style>
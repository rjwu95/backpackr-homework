<template>
  <div class="container" :style="{ width }">
    <img :src="image">
    <VerticalContent
      :label="label"
      :title="title"
      :hilight="hilight"
      :crossOut="crossOut"
      :rating="rating"
      :description="description"
    />
  </div>
</template>

<script>
import VerticalContent from './VerticalContent.vue'

export default {
  name: 'VerticalCard',
  components: { VerticalContent },
  props: {
    image: {
      type: String,
      default: 'https://www.spartacapital.com/wp-content/uploads/2019/04/Sample-Logo-square.png'
    },
    label: {
      type: String,
    },
    title: {
      type: String,
    },
    hilight: {
      type: String,
    },
    crossOut: {
      type: String,
    },
    rating: {
      type: Number,
    },
    description: {
      type: String,
    },
    width: {
      type: String,
      default: '300px'
    }
  }
}
</script>

<style scoped>
.container {
  border: solid;
  display: flex;
  margin-right: 50px;
  flex-direction: column;
}
img { 
  width: 100%;
  height: auto;
}
</style>
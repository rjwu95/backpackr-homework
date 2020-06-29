<template>
  <div class="container">
    <img :src="image">
    <HorizontalContent
      :title="title"
      :rating="rating"
      :description="description"
      :writer="writer"
    />
  </div>
</template>

<script>
import HorizontalContent from './HorizontalContent.vue'

export default {
  name: 'HorizontalCard',
  components: { HorizontalContent },
  props: {
    image: {
      type: String,
      default: 'https://www.spartacapital.com/wp-content/uploads/2019/04/Sample-Logo-square.png'
    },
    title: {
      type: String,
    },
    rating: {
      type: Number,
    },
    description: {
      type: String,
    },
    writer: {
      type: String,
    },
    height: {
      type: String,
      default: '250px'
    },
    width: {
      type: String,
      default: '800px'
    }
  }
}
</script>

<style scoped>
.container {
  border: solid;
  display: flex;
  margin-right: 50px;
  flex-direction: row;
}
img { 
  height: 100%;
  width: auto;
}
</style>
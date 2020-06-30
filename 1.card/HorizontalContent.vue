<template>
  <div class="horizontal-content">
    <p class="bold singleline-description">{{ title }}</p>
    <p class="multiline-description">{{ description }}</p>
    <div>
      <span v-for="n in 5" class="icon" :key="n" :class="{ selected: n <= rating }">★</span>
      <span> | {{ writer }}</span>
    </div>
  </div>
</template>

<script>

const LOREM = 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Molestias ea modi esse a tenetur, maxime ratione velit quod repellendus veniam voluptas voluptates quaerat, provident itaque voluptatem quae. Harum, laboriosam earum?'

export default {
  name: 'HorizontalContent',
  props: {
    rating: {
      type: Number,
      default: 3
    },
    description: {
      type: String,
      default: LOREM
    },
    title: {
      type: String,
      default: LOREM
    },
    writer: {
      type: String,
      default: 'John Doe'
    }
  }
}
</script>

<style scoped>
.horizontal-content {
  overflow: hidden;
  display: block;
  padding: 0 10px;
}
.singleline-description {
  white-space: nowrap; 
  overflow: hidden;
  text-overflow: ellipsis; 
}
.multiline-description {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}
.icon {
  color: #aaaaaa
}
.icon.selected {
  color: #ffbe3f
}
.bold {
  font-weight: bold;
}
</style>
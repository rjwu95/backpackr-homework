<template>
  <div class="container">
    <img :src="image">
    <div class="horizontal-content">
      <p class="bold singleline-description">{{ title }}</p>
      <p class="multiline-description">{{ description }}</p>
      <div>
        <span v-for="n in 5" class="icon" :key="n" :class="{ selected: n <= rating }">★</span>
        <span> | {{ writer }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HorizontalCard',
  props: {
    image: {
      type: String,
      default: 'https://www.spartacapital.com/wp-content/uploads/2019/04/Sample-Logo-square.png'
    },
    title: {
      type: String,
      default: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Molestias ea modi esse a tenetur, maxime ratione velit quod repellendus veniam voluptas voluptates quaerat, provident itaque voluptatem quae. Harum, laboriosam earum?'
    },
    rating: {
      type: Number,
      default: 3
    },
    description: {
      type: String,
      default: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Molestias ea modi esse a tenetur, maxime ratione velit quod repellendus veniam voluptas voluptates quaerat, provident itaque voluptatem quae. Harum, laboriosam earum?'
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
  flex-direction: column;
  justify-content: space-between;
  align-items: flex-start;
  overflow: hidden;
  display: block;
  padding: 0 10px;
}
.container {
  border: solid;
  display: flex;
  margin-right: 50px;
  flex-direction: row;
  height: 250px;
  width: 800px
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
img { 
  height: 100%;
  width: auto;
}
.bold {
  font-weight: bold;
}
</style>
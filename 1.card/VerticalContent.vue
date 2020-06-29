<template>
  <div>
    <div class="vertical-content">
      <div class="title-container">
        <div class="card-label">{{ label }}</div>
        <div class="bold">{{ title }}</div>
        <div class="feature">
          <span class="hilight">{{ hilight }}</span>
          <span class="cross-out">{{ crossOut }}</span>
        </div>
      </div>
      <div class="description-container">
        <div class="rating">
          <span v-for="n in 5" class="icon" :key="n" :class="{ selected: n <= rating }">★</span>
        </div>
        <p class="vertical-description singleline-description">{{ description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
const LOREM = 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Molestias ea modi esse a tenetur, maxime ratione velit quod repellendus veniam voluptas voluptates quaerat, provident itaque voluptatem quae. Harum, laboriosam earum?'

export default {
  name: 'VerticalContent',
  props: {
    label: {
      type: String,
      default: 'Card Label'
    },
    title: {
      type: String,
      default: 'Card Title'
    },
    hilight: {
      type: String,
      default: 'Hilight'
    },
    crossOut: {
      type: String,
      default: 'Cross Out'
    },
    rating: {
      type: Number,
      default: 3
    },
    description: {
      type: String,
      default: LOREM
    }
  }
}
</script>

<style scoped>
.singleline-description {
  white-space: nowrap; 
  overflow: hidden;
  text-overflow: ellipsis; 
}
.title-container {
  border-bottom: solid;
  overflow: hidden;
  display: block;
  align-items: flex-start;
  flex-direction: column;
  padding: 0 10px;
}
.icon {
  color: #aaaaaa
}
.icon.selected {
  color: #ffbe3f
}
.description-container {
  overflow: hidden;
  padding: 10px 10px;
  height: 76px;
  text-align: left;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.card-label {
  margin-top: 5px;
  color: gray;
}
.feature {
  margin-top: 15px;
}
.hilight {
  color: red;
  margin-right: 3px;
}
.cross-out {
  text-decoration: line-through;
  font-size: 12px;
  color: gray;
}
.bold {
  font-weight: bold;
}
</style>
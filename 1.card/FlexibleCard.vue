<template>
  <div class="flexible-container">
    <img :src="image">
    <div class="vertical-content">
      <div class="title-container">
        <div class="card-label">{{ label }}</div>
        <div class="card-title">{{ title }}</div>
        <div class="hilight">{{ hilight }}</div>
      </div>
      <div class="description-container">
        <div class="rating">
          <span v-for="n in 5" class="icon" :key="n" :class="{ selected: n <= rating }">★</span>
        </div>
        <p class="vertical-description singleline-description">{{ description }}</p>
      </div>
    </div>
    <div class="horizontal-content">
      <p class="bold singleline-description">{{ horizontalTitle }}</p>
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
  name: 'FlexibleCard',
  props: {
    image: {
      type: String,
      default: 'https://www.spartacapital.com/wp-content/uploads/2019/04/Sample-Logo-square.png'
    },
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
    rating: {
      type: Number,
      default: 3
    },
    description: {
      type: String,
      default: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Molestias ea modi esse a tenetur, maxime ratione velit quod repellendus veniam voluptas voluptates quaerat, provident itaque voluptatem quae. Harum, laboriosam earum?'
    },
    horizontalTitle: {
      type: String,
      default: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Molestias ea modi esse a tenetur, maxime ratione velit quod repellendus veniam voluptas voluptates quaerat, provident itaque voluptatem quae. Harum, laboriosam earum?'
    },
    verticalWidth: {
      type: Number,
      default: 300
    },
    horizontalWidth: {
      type: Number,
      default: 800
    },
    horizontalHeight: {
      type: Number,
      default: 250
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
.flexible-container {
  border: solid;
  display: flex;
  margin-right: 50px;
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
@media screen and (max-height: 440px) {
  .flexible-container {
    flex-direction: row;
    width: 800px;
    height: 250px;
  }
  .vertical-content {
    display: none !important;
  }
  img { 
    height: 100%;
    width: auto;
  }
}
@media screen and (min-height: 441px) {
  .flexible-container {
    flex-direction: column;
    width: 300px;
  }
  .horizontal-content {
    display: none !important;
  }
  img { 
    width: 100%;
    height: auto;
  }
}
@media screen and (max-height: 480px) {
  .description-container {
    display: none !important;
  }
  .title-container {
    border-bottom: none !important;
  }
}
@media screen and (max-height: 530px) {
  .vertical-description {
    display: none !important;
  }
}
.card-title {
  font-weight: bold;
}
.card-label {
  margin-top: 5px;
  color: gray;
}
.hilight {
  margin-top: 15px;
  color: red
}
.bold {
  font-weight: bold;
}
</style>
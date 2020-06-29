<template>
  <div class="vertical-content">
    <div class="title-container">
      <div class="card-label">Card Label</div>
      <div class="card-title">Card Title</div>
      <div class="hilight">Hilight</div>
    </div>
    <div class="description-container">
      <div class="rating">
        <span v-for="n in 5" class="icon" :key="n" :class="{ selected: n <= rating }">★</span>
      </div>
      <p class="vertical-description singleline-description">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Molestias ea modi esse a tenetur, maxime ratione velit quod repellendus veniam voluptas voluptates quaerat, provident itaque voluptatem quae. Harum, laboriosam earum?</p>
    </div>
</div>
</template>

<script>
export default {
  name: 'VerticalContent'
}
</script>

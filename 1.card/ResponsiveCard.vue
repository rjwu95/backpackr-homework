<template>
  <div
    class="responsive-container"
    ref="responsiveContainer"
    :style="{ width: containerWidth, height: containerHeight, 'flex-direction': responsiveDirection }"
  >
    <img :src="image" :width="imageWidth" :height="imageHeight">
    <VerticalContent
      class="vertical-child"
      :label="label"
      :title="title"
      :hilight="hilight"
      :crossOut="crossOut"
      :description="description"
      :rating="rating"
    />
    <HorizontalContent 
      class="horizontal-child"
      :title="horizontalTitle"
      :description="description"
      :rating="rating"
      :writer="writer"
    />
  </div>
</template>

<script>
import VerticalContent from './VerticalContent.vue'
import HorizontalContent from './HorizontalContent.vue'

export default {
  name: 'ResponsiveCard',
  components: { VerticalContent, HorizontalContent },
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
    horizontalTitle: {
      type: String,
    },
    verticalWidth: {
      type: String,
      default: '300px'
    },
    horizontalWidth: {
      type: String,
      default: '800px'
    },
    horizontalHeight: {
      type: String,
      default: '250px'
    },
    writer: {
      type: String,
    },
    changeDirectionHeight: {
      type: String,
      default: '440px'
    }
  },
  data() {
    return {
      containerWidth: '',
      containerHeight: '',
      matchHeight: null,
      responsiveDirection: '',
      imageWidth: '',
      imageHeight: ''
    }
  },
  mounted() {
    this.matchHeight = window.matchMedia(`(max-height: ${this.changeDirectionHeight})`)
    this.changeCardDirection(this.matchHeight)
    this.matchHeight.addListener(this.changeCardDirection)
  },
  destroyed() {
    this.matchHeight.removeListener(this.changeCardDirection)
  },
  methods: {
    changeCardDirection(target) {
      if (target.matches) {
        this.containerHeight = this.horizontalHeight
        this.containerWidth = this.horizontalWidth
        this.responsiveDirection = 'row'
        this.imageWidth = 'auto'
        this.imageHeight = '100%'
        document.querySelector('.vertical-content').style.display = 'none'
        document.querySelector('.horizontal-content').style.display = 'block'
      } else {
        this.containerWidth = this.verticalWidth
        this.containerHeight = 'auto'
        this.responsiveDirection = 'column'
        this.imageWidth ='100%'
        this.imageHeight = 'auto'
        document.querySelector('.vertical-content').style.display = 'block'
        document.querySelector('.horizontal-content').style.display = 'none'
      }
    }
  }
}
</script>

<style scoped>
.responsive-container {
  border: solid;
  display: flex;
  margin-right: 50px;
}
@media screen and (max-height: 480px) {
  .vertical-child >>> .description-container {
    display: none !important;
  }
  .vertical-child >>> .title-container {
    border-bottom: none !important;
  }
}
@media screen and (max-height: 530px) {
  .vertical-child >>> .vertical-description {
    display: none !important;
  }
}
</style>
<template>
  <div
    class="responsive-container"
    ref="responsiveContainer"
    :style="{ width: containerWidth, height: containerHeight, 'flex-direction': responsiveDirection }"
  >
    <img :src="image" :width="imageWidth" :height="imageHeight">
    <VerticalContent
      :label="label"
      :title="title"
      :hilight="hilight"
      :crossOut="crossOut"
      :description="description"
      :rating="rating"
    />
    <HorizontalContent 
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
    heightOfChangeDirectionPoint: {
      type: String,
      default: '440px'
    },
    heightOfVisibleRatingBoxPoint: {
      type: String,
      default: '480px'
    },
    heightOfVisibleDescriptionPoint: {
      type: String,
      default: '530px'
    }
  },
  data() {
    return {
      containerWidth: '',
      containerHeight: '',
      matchChangeDirectionPoint: null,
      matchVisibleRatingBoxPoint: null,
      matchVisibleDescriptionPoint: null,
      responsiveDirection: '',
      imageWidth: '',
      imageHeight: ''
    }
  },
  mounted() {
    this.addListenerDependingHeight()
  },
  destroyed() {
    this.removeListenerDependingHeight()
  },
  methods: {
    addListenerDependingHeight() {
      this.matchChangeDirectionPoint = this.matchHeight(this.heightOfChangeDirectionPoint)
      this.matchVisibleRatingBoxPoint = this.matchHeight(this.heightOfVisibleRatingBoxPoint)
      this.matchVisibleDescriptionPoint = this.matchHeight(this.heightOfVisibleDescriptionPoint)
      this.changeCardDirection(this.matchChangeDirectionPoint)
      this.changeVisibleRatingBox(this.matchVisibleRatingBoxPoint)
      this.changeVisibleDescription(this.matchVisibleDescriptionPoint)
      this.matchChangeDirectionPoint.addListener(this.changeCardDirection)
      this.matchVisibleRatingBoxPoint.addListener(this.changeVisibleRatingBox)
      this.matchVisibleDescriptionPoint.addListener(this.changeVisibleDescription)
    },
    removeListenerDependingHeight() {
      this.matchChangeDirectionPoint.removeListener(this.changeCardDirection)
      this.matchVisibleRatingBoxPoint.removeListener(this.changeVisibleRatingBox)
      this.matchVisibleDescriptionPoint.removeListener(this.changeVisibleDescription)
    },
    matchHeight(height) {
      return window.matchMedia(`(max-height: ${height})`)
    },
    changeCardDirection(target) {
      const verticalContent = document.querySelector('.responsive-container .vertical-content')
      const horizontalContent = document.querySelector('.responsive-container .horizontal-content')
      if (target.matches) {
        this.containerHeight = this.horizontalHeight
        this.containerWidth = this.horizontalWidth
        this.responsiveDirection = 'row'
        this.imageWidth = 'auto'
        this.imageHeight = '100%'
        verticalContent.style.display = 'none'
        horizontalContent.style.display = 'block'
      } else {
        this.containerHeight = 'auto'
        this.containerWidth = this.verticalWidth
        this.responsiveDirection = 'column'
        this.imageWidth ='100%'
        this.imageHeight = 'auto'
        verticalContent.style.display = 'block'
        horizontalContent.style.display = 'none'
      }
    },
    changeVisibleRatingBox(target) {
      const ratingBox = document.querySelector('.responsive-container .vertical-content .description-container')
      const titleContainer = document.querySelector('.responsive-container .vertical-content .title-container')
      if (target.matches) {
        ratingBox.style.display = 'none'
        titleContainer.style['border-bottom'] = 'none'
      } else {
        ratingBox.style.display = 'flex'
        titleContainer.style['border-bottom'] = 'solid'
      }
    },
    changeVisibleDescription(target) {
      const description = document.querySelector('.responsive-container .vertical-content .vertical-description')
      if (target.matches) {
        description.style.display = 'none'
      } else {
        description.style.display = 'block'
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
</style>
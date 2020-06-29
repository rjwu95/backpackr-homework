<template>
  <div
    class="responsive-container"
    ref="responsiveContainer"
    :style="{ width: containerWidth, height: containerHeight }"
  >
    <img :src="image">
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
    }
  },
  data() {
    return {
      containerWidth: '',
      containerHeight: '',
      matchHeight: null
    }
  },
  mounted() {
    this.matchHeight = window.matchMedia("(max-height: 440px)")
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
      } else {
        this.containerWidth = this.verticalWidth
        this.containerHeight = 'auto'
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
@media screen and (max-height: 440px) {
  .responsive-container {
    flex-direction: row;
  }
  .vertical-child >>> .vertical-content {
    display: none !important;
  }
  img { 
    height: 100%;
    width: auto;
  }
}
@media screen and (min-height: 441px) {
  .responsive-container {
    flex-direction: column;
  }
  .horizontal-child >>> .horizontal-content {
    display: none !important;
  }
  img { 
    width: 100%;
    height: auto;
  }
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
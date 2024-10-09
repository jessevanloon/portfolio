<script>
import { VueMarqueeSlider } from 'vue3-marquee-slider';
import '../node_modules/vue3-marquee-slider/dist/style.css'

export default {
  components: {
    VueMarqueeSlider
  }
}

</script>

<template>
  <div class="slider-wrapper">
    <vue-marquee-slider
    id="marquee-slider-loop"
    :speed="40000"
    :space="20"
    :width="400"
  >
    <div :key="1" class="item"><span class="dot"></span>Brand design</div>
    <div :key="2" class="item"><span class="dot"></span>Website design</div>
    <div :key="3" class="item"><span class="dot"></span>Website development</div>
    <div :key="4" class="item"><span class="dot"></span>Software development</div>
    <div :key="5" class="item"><span class="dot"></span>E-commerce solutions</div>
  </vue-marquee-slider>
  </div>
</template>

<style scoped>
.slider-wrapper{
  padding: 100px 0;
  background-color: #ffffff;
  /* background-image: url('/watercolor-paper-texture.jpg'); */
  background-position: center center;
  position: relative;
  overflow: hidden;
  border-radius: 0 0 140px 140px;
}

.dot{
  width: 10px;
  height: 10px;
  border-radius: 100%;
  background: #000;
  display: block;
}


.item{
  text-align: center;
  font-size: 32px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
}

@media(max-width: 767px){
  .slider-wrapper{
    padding: 80px 0;
  }
}
</style>
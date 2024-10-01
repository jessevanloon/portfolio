<script>
// import { gsap } from "gsap";

// export default {
//   mounted() {
//     this.animateBackground();

//   },
//   methods: {
//     animateBackground() {
//       gsap.to(".services-wrap", {
//         backgroundPosition: "calc(50% + 30px) calc(50% - 30px)",
//         duration: 20,
//         ease: "sine.inOut",
//         repeat: -1,
//         yoyo: true
//       });
//     }
//   }
// }
</script>

<template>
  <div class="services-wrap">
    <div class="container mx-auto">
      <div class="services"></div>
    </div>
  </div>
</template>

<style scoped>
.services-wrap{
  padding: 80px 0;
  border-radius: 140px 140px 0 0;
  background-image: url('/textured-paper.png');
  /* background-size: 110% 110%; */
  background-position: center center;
  position: relative;
  overflow: hidden;
}
</style>
<script setup>
import { onMounted } from 'vue'
import { gsap } from 'gsap'

const services = ref([
  { key: 1, text: 'Brand design' },
  { key: 2, text: 'Website design' },
  { key: 3, text: 'Website development' },
  { key: 4, text: 'Software development' },
  { key: 5, text: 'E-commerce solutions' }
])


onMounted(() => {
  let tween = gsap.to('.marquee__part', {
    xPercent: -100,
    repeat: -1,
    duration: 25, // Dit is de scroll snelheid in seconden
    ease: 'linear'
  }).totalProgress(0.5);

  gsap.set('.marquee__inner', {
    xPercent: -50
  });

  // Optioneel, voor een leuk extra effect de marquee scroll richting veranderen
  let currentScroll = 0;
  let isScrollingDown = true;
  
  window.addEventListener('scroll', () => {
    if (window.scrollY > currentScroll) {
      isScrollingDown = true;
    } else {
      isScrollingDown = false;
    }

    gsap.to(tween, {
      timeScale: isScrollingDown ? 1 : -1
    });

    currentScroll = window.scrollY;
  });
});
</script>

<template>
  <!-- ... bestaande code ... -->
   <div class="marquee-wrap">
  <section class="marquee">
    <div class="marquee__inner">
      <div v-for="i in 4" :key="'part-' + i" class="marquee__part">
          <span v-for="service in services" :key="'item-' + service.key" class="marquee__item">
            <span class="dot"></span>{{ service.text }}
          </span>
        </div>
    </div>
    </section>
  </div>
</template>

<style scoped>
.marquee-wrap{
  padding: 60px 0;
}
.marquee {
  position: relative;
  overflow: hidden;

  height: fit-content;

  background: #fff;
  padding: 16px;
}

.marquee__inner {
  -webkit-font-smoothing: antialiased;
  width: fit-content;
  display: flex;
  flex: auto;
}

.marquee__part {
  flex-shrink: 0;
  font-smooth: always;

  color: #000;

  /* text-transform: uppercase; */
  font-weight: 800;
  font-size: 40px;

  display: flex;
  gap: 32px;
  padding: 0 16px;

  font-family: 'Otterco', sans-serif;
}
</style>
<script setup>
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

const servicesWrap = ref(null)

onMounted(() => {
  // Initialiseer ScrollTrigger en detecteer de scrollrichting
  let lastScrollTop = 0

  gsap.from(servicesWrap.value, {
    opacity: 0,
    y: 100,
    duration: 1,
    scrollTrigger: {
      trigger: servicesWrap.value,
      start: 'top 80%',
      end: 'bottom 20%',
      toggleActions: 'play none none reverse',
      onUpdate: (self) => {
        let currentScrollTop = self.scroller.scrollTop || window.pageYOffset
        if (currentScrollTop > lastScrollTop) {
          // Speel de animatie alleen als er naar beneden wordt gescrold
          gsap.to(servicesWrap.value, { opacity: 1, y: 0, duration: 1 })
        }
        lastScrollTop = currentScrollTop
      }
    }
  })
})
</script>


<template>
  <div class="services-wrap" ref="servicesWrap">
    <div class="container mx-auto">
      <div class="services-content flex flex-col items-center justify-center gap-16">
        <div class="title-wrap">
          <div class="title title-font">Collaborate with brands and agencies to create impactful results.</div>
        </div>
        <div class="services flex">
          <div class="btn-wrap">
            <a class="btn orange">Services</a>
          </div>
          <div class="services-inner flex justify-center items-center mt-8 gap-8">
            <div class="service">
              <div class="first-block">
                <div class="image-wrap">
                  <img src="/svgs/website-design.svg" />
                </div>
                <div class="service-title">UX & UI</div>
              </div>
              <div class="text">Designing interfaces that are intuitive, efficient, and enjoyable to use.</div>
            </div>
            <div class="service">
              <div class="first-block">
                <div class="image-wrap">
                  <img src="/svgs/mobile-design.svg" />
                </div>
                <div class="service-title">Web & Mobile App</div>
              </div>
              <div class="text">Transforming ideas into exceptional web and mobile app experiences.</div>
            </div>
            <div class="service">
              <div class="first-block">
              <div class="image-wrap">
                <img src="/svgs/creative-design.svg" />
              </div>
              <div class="service-title">Design & Creative</div>
              </div>
              <div class="text">Crafting visually stunning designs that connect with your audience.</div>
            </div>
            <div class="service">
              <div class="first-block">
                <div class="image-wrap">
                  <img src="/svgs/development.svg" />
                </div>
                <div class="service-title">Development</div>
              </div>
              <div class="text">Bringing your vision to life with the latest technology and design trends.</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.services-wrap{
  padding: 80px 0;
  border-radius: 120px 120px 120px 120px;
  /* background-image: url('/textured-paper.png');
  background-position: center center; */
  background: #eee;
}

.services-wrap .title-wrap .title{
  font-size: 32px;
  font-weight: 600;
  max-width: 600px;
  text-align: center;
}

.services-wrap .services{
  position: relative;
  padding-top: 40px;
  border-top: 1px solid #fff;
  display: flex;
  justify-content: center;
}

.services-wrap .services .service .image-wrap{
  display: flex;
  align-items: center;
}

.services-wrap .services .service img{
  height: 60px;
  width: 60px;
}

.services-wrap .services .btn-wrap{
  position: absolute;
  top: -30px;
}

.services-wrap .services .btn-wrap .btn.orange{
  transform: rotate(-10deg);
  width: 120px;
}

.services-wrap .services-inner{
  max-width: 1200px;
  align-items: stretch;
}

.services-wrap .service{
  display: flex;
  flex-direction: column;
  gap: 12px;
  flex: 1;
}

.services-wrap .service .service-title{
  font-weight: 500;
  font-size: 18px;
}

.services-wrap .service .text{
  max-width: 220px;
}

.services-wrap .service .first-block{
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 8px;
  flex: 1;
}

@media(max-width: 767px){
  .services-wrap{
    border-radius: 80px;
  }
  .services-content{
    padding: 0 12px;
  }
  .services-wrap .title-wrap .title{
    font-size: 28px;
  }
  .services-wrap .services{
    width: 100%;
  }
  .services-wrap .services-inner{
    flex-direction: column;
    width: 100%;
    padding: 0 12px;
  }
  .services-wrap .service{
    flex: unset;
    width: 100%;
    /* flex-direction: row; */
    align-items: center;
  }
  .services-wrap .service .text{
    max-width: none;
    text-align: center;
  }
  .services-wrap .service .first-block{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 4px;
    flex: 1;
  }
  .services-wrap .services .btn-wrap .btn{
    background: rgb(36, 36, 36) !important;
  }
}
</style>
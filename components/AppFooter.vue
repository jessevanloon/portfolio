<script setup>
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

const footerWrap = ref(null)
const animationPlayed = ref(false)

onMounted(() => {
  const tl = gsap.timeline({
    scrollTrigger: {
      trigger: footerWrap.value,
      start: 'top 80%',
      end: 'bottom 20%',
      once: true, // Zorgt ervoor dat de animatie slechts één keer wordt afgespeeld
      onEnter: () => {
        if (!animationPlayed.value) {
          tl.to(footerWrap.value, {
            opacity: 1,
            y: 0,
            duration: 1,
            onComplete: () => {
              animationPlayed.value = true
            }
          })
        }
      }
    }
  })

  // Stel de initiële staat in
  gsap.set(footerWrap.value, { opacity: 0, y: 100 })
})
</script>



<template>
  <div class="footer" ref="footerWrap">
    <div class="container mx-auto">
      <div class="footer-inner">
        <div class="icon-wrap">
          <img src="/svgs/shake-hand-new.svg" />
        </div>
        <div class="title-wrap">
          <div class="title">Tell me about your next project</div>
        </div>
        <div class="btn-wrap">
          <a href="mailto:jesseruben.vanloon@gmail.com" target="_blank" class="btn"><Icon name="bx:bx-envelope" />Email me</a>
          <a href="https://wa.me/31623214337" target="_blank" class="btn second"><Icon name="bx:bxl-whatsapp" />Whatsapp</a>
        </div>
      </div>
      <div class="footer-bottom">
        <div class="copy-text">© 2024 All rights reserved.</div>
        <div class="bottom-links">
          <a href="https://www.instagram.com/jesse.vanloon">Instagram</a>
          <div>/</div>
          <a href="https://www.linkedin.com/in/jesse-van-loon-8b3a751a2/">Linkedin</a>
          <!-- <div>/</div>
          <a href="https://x.com/jesse_vanloon">Twitter</a> -->
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.footer{
  background: #fff;
  border-radius: 140px 140px 0 0;
}

.footer .footer-inner{
  padding-top: 120px;
  padding-bottom: 80px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 40px;
}

.footer .footer-inner .icon-wrap{
  display: flex;
  justify-content: center;
  align-items: center;
}

.footer .footer-inner .icon-wrap img{
  width: 100px;
  height: 100px;
}

.footer .footer-inner .title-wrap .title{
  font-size: 40px;
  font-weight: 600;
  max-width: 500px;
  text-align: center;
}

.footer .footer-inner .btn-wrap{
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 20px;
}

.footer .footer-inner .btn-wrap .btn.second{
  background: #eee;
  color: rgb(36, 36, 36);
}

.footer .footer-inner .btn-wrap span{
  font-size: 20px;
}

.footer-bottom{
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 40px 0;
  border-top: 1px solid #eee;
}

.footer-bottom .bottom-links{
  display: flex;
  align-items: center;
  gap: 8px;
}
@media(max-width: 767px){
  .footer .footer-inner{
    padding: 80px 0;
    gap: 20px;
  }
  .footer .footer-inner .btn-wrap{
    flex-direction: column;
  }
  .footer-bottom{
    flex-direction: column-reverse;
    gap: 12px;
    padding: 20px 0;
  }
}
</style>

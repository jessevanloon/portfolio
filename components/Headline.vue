
<script>
import { gsap } from "gsap";

export default {
  mounted() {
    this.animateProfileImage();
    this.animateImageLabel();
    // this.setupButtonAnimation();
    // this.animateBackground();

  },
  methods: {
    animateProfileImage() {
      gsap.from(".content-holder", {
        opacity: 0,
        scale: 0.5,
        duration: 1,
        ease: "power2.out"
      });
    },
    animateImageLabel() {
      gsap.to(".image-label", {
        y: -10,
        duration: 1.5,
        ease: "power1.inOut",
        yoyo: true,
        repeat: -1
      });
    },
    // animateBackground() {
    //   gsap.to(".full-headline-wrap", {
    //     backgroundPosition: "calc(50% + 30px) calc(50% - 30px)",
    //     duration: 10,
    //     ease: "sine.inOut",
    //     repeat: -1,
    //     yoyo: true
    //   });
    // }
  }
}
</script>

<template>
  <div class="full-headline-wrap">
    <div class="header-wrap">
    <div class="container mx-auto">
      <div class="inner flex justify-between">
        <div class="email flex items-center gap-2	">
          <div>Front-end by Jesse</div>
        </div>
        <div class="social-icons flex items-center gap-4">
          <div class="instagram flex items-center">
            <a href="https://www.instagram.com/jesse.vanloon" target="_blank" rel="noopener noreferrer" class="flex items-center">
              <Icon name="bx:bxl-instagram" />
            </a>
          </div>
          <div class="linkedin flex items-center">
            <a href="https://www.linkedin.com/in/jesse-van-loon-8b3a751a2/" target="_blank" rel="noopener noreferrer" class="flex items-center">
              <Icon name="bx:bxl-linkedin" />
            </a>
          </div>
          <div class="twitter flex items-center">
            <a href="https://x.com/jesse_vanloon" target="_blank" rel="noopener noreferrer" class="flex items-center">
            <Icon name="bx:bxl-twitter" />
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="headline-wrap">
    <div class="container mx-auto">
      <div class="inner flex justify-center items-center">
        <div class="content-holder flex flex-col">
          <div class="image-wrap flex items-center justify-center">
            <div class="image-holder">
              <img src="/public/profile-image.jpeg" />
                <div class="image-label">Jesse van Loon <span>👋</span></div>
            </div>
          </div>
          <h1 class="title title-font text-center">Building digital products, brands, and experiences.</h1>
          <div class="btn-wrap flex items-center justify-center mt-6">
            <a href="mailto:jesseruben.vanloon@gmail.com" target="_blank" class="btn">Work together</a>
            <!-- <LottieAnimation src="animations/lightning.json" /> -->
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<style scoped>
.full-headline-wrap{
  border-radius: 0 0 140px 140px;
  /* background-image: url('/textured-paper.png');
  background-position: center center; */
  background: #eee;
  position: relative;
  overflow: hidden;
}

.inner{
  padding: 16px 0;
}

.inner .email{
  font-size: 22px;
  font-weight: 500;
}

.social-icons span{
  font-size: 26px;
}

.headline-wrap{
  padding: 90px 0;
}

.headline-wrap .content-holder{
  max-width: 520px;
}

.image-wrap{
  width: 100%;
  height: auto;
  max-width: 100%;
  max-height: 100%;
}

.image-wrap img{
  width: 100%;
  height: 100%;
  max-width: 100px;
  max-height: 100px;
  border-radius: 100%;
}

.image-wrap .image-holder{
  position: relative;
}

.image-wrap .image-holder .image-label{
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  box-shadow: rgba(236, 235, 234, 0.4) 0px 20px 10px 0px;
  position: absolute;
  top: 0;
  right: -120px;
  background: #fff;
  border-radius: 60px;
  padding: 12px;
  font-size: 14px;
  transform: rotate(-10deg);
  width: 140px;
}

.headline-wrap .btn{
  background: rgb(255, 101, 0);
}


@media(max-width: 767px){
  .full-headline-wrap{
    border-radius: 0 0 80px 80px;
  }
  .inner{
    padding: 16px 12px;
  }
  .inner .email{
    font-size: 18px;
  }
  .social-icons span{
    font-size: 22px;
  }
  .headline-wrap{
    padding: 40px 0;
    padding-bottom: 60px;
  }
  .image-wrap{
    margin-bottom: 20px;
  }
}
</style>
<template>
  <div class="services-wrap">
    <div class="container mx-auto">
      <div class="services-content flex flex-col items-center justify-center gap-16">
        <div class="title-wrap">
          <div class="title title-font">Collaborate with brands and agencies to create impactful results.</div>
        </div>
        <div class="services flex">
          <div class="btn-wrap">
            <a class="btn light">Services</a>
          </div>
          <div class="services-inner flex justify-center items-center mt-8 gap-8">
            <div class="service">
              <LottieAnimation src="/animations/lightning.json" />
              <div class="service-title">UX & UI</div>
              <div class="text">Designing interfaces that are intuitive, efficient, and enjoyable to use.</div>
            </div>
            <div class="service">
              <LottieAnimation src="/animations/lightning.json" />
              <div class="service-title">Web & Mobile App</div>
              <div class="text">Transforming ideas into exceptional web and mobile app experiences.</div>
            </div>
            <div class="service">
              <LottieAnimation src="/animations/lightning.json" />
              <div class="service-title">Design & Creative</div>
              <div class="text">Crafting visually stunning designs that connect with your audience.</div>
            </div>
            <div class="service">
              <LottieAnimation src="/animations/lightning.json" />
              <div class="service-title">Development</div>
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
  border-radius: 140px 140px 0 0;
  background-image: url('/textured-paper.png');
  background-position: center center;
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

.services-wrap .services svg{
  height: 100px;
}

.services-wrap .services .btn-wrap{
  position: absolute;
  top: -30px;
}

.services-wrap .services .btn-wrap .btn.light{
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
</style>
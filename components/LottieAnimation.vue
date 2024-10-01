<template>
  <div class="lottie" ref="container"></div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { useNuxtApp } from '#app'

const props = defineProps({
  src: {
    type: String,
    required: true
  }
})

const container = ref(null)
const { $lottie } = useNuxtApp()

onMounted(() => {
  $lottie.loadAnimation({
    container: container.value,
    renderer: 'svg',
    loop: true,
    autoplay: true,
    path: props.src
  })
})
</script>

<style>
.lottie{
  height: 100px;
  width: fit-content;
}
</style>
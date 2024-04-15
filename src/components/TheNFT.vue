<script setup>
import { onMounted, ref } from 'vue'
import nft1 from '~/assets/owl1.png'
import nft2 from '~/assets/owl2.png'
import nft3 from '~/assets/owl3.png'
import nft4 from '~/assets/owl4.png'

const images = [nft1, nft2, nft3, nft4]

const observer = ref(null)

onMounted(() => {
  observer.value = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        startAnimations()
        observer.value.disconnect()
      }
    })
  })

  observer.value.observe(document.querySelector('.nft-container'))
})

function startAnimations() {
  const owlImages = document.querySelectorAll('.owl-animation')
  owlImages.forEach((owl) => {
    owl.style.opacity = '0'
    owl.style.transform = `translate(${getRandomInt(-100, 100)}vw, ${getRandomInt(-100, 100)}vh) scale(0)`
    owl.animate(
      [
        { opacity: '0', transform: `translate(${getRandomInt(-100, 100)}vw, ${getRandomInt(-100, 100)}vh) scale(0)` },
        { opacity: '1', transform: 'translate(0, 0) scale(1)' },
      ],
      {
        duration: 1000,
        easing: 'ease-out',
        fill: 'forwards',
        delay: getRandomInt(0, 1000),
      },
    )
  })
}

function getRandomInt(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min
}
</script>

<template>
  <div class="z-0 flex items-center justify-center p-8">
    <div class="mx-auto max-w-screen-lg px-2">
      <div class="nft-container grid grid-cols-2 cursor-pointer gap-4 sm:grid-cols-4">
        <img
          v-for="(image, index) in images"
          :key="index"
          :src="image"
          alt="Night Owls Gif"
          class="owl-animation h-auto w-full object-cover"
          style="transition: transform 0.5s ease, opacity 0.5s ease; opacity: 0.5;"
        >
      </div>
    </div>
  </div>
</template>

<style scoped>
.owl-animation {
  transition:
    transform 0.5s ease,
    opacity 0.5s ease;
}

.owl-animation:hover {
  transform: scale(1.1) !important;
  opacity: 1 !important;
}
</style>

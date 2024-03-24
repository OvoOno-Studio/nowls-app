<script setup>
import { onMounted, ref } from 'vue'
import logofull from '~/assets/logofull.jpg'
import owl from '~/assets/owl.gif'

const progress = ref(0)
const circleLength = 283
const showScrollToTop = ref(false)

function updateProgressCircle() {
  const totalHeight = document.body.scrollHeight - window.innerHeight
  const scrolled = window.pageYOffset
  progress.value = (scrolled / totalHeight) * 100

  const offset = circleLength * (1 - progress.value / 100)
  const circle = document.querySelector('.progress-circle-bar')
  circle.style.strokeDashoffset = offset

  showScrollToTop.value = scrolled > 0.9 * totalHeight
}

function scrollToTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

onMounted(() => {
  updateProgressCircle()
  window.addEventListener('scroll', updateProgressCircle)
})
</script>

<template>
  <!-- progress circle -->
  <div class="progress-circle-container">
    <svg class="progress-circle" viewBox="0 0 100 100">
      <circle class="progress-background" cx="50" cy="50" r="45" />
      <circle :style="{ strokeDashoffset: circleLength - (progress * circleLength / 100) }" class="progress-circle-bar" cx="50" cy="50" r="45" />
    </svg>
    <div class="scroll-to-top" @click="scrollToTop">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <path d="M12 19V5M5 12l7-7 7 7" />
      </svg>
    </div>
  </div>
  <div class="h-screen container">
    <div class="content min-h-screen min-w-full flex items-center justify-center">
      <div flex items-center justify-center>
        <img
          :src="owl" alt="Night Owls Gif" class="ml-0 lg:ml-80"
        >
      </div>
    </div>
    <div class="content min-h-screen min-w-full flex items-center justify-center text-7xl lg:text-9xl">
      <TypeWritter text="Night Owl's" :changeable="true" />
    </div>

    <div class="content min-h-screen min-w-full flex items-center justify-center">
      <TypeWritter text="Sollana." :changeable="true" class="text-7xl lg:text-9xl" />
    </div>
    <div class="content mb-20 min-h-screen min-w-full flex items-center">
      <TypeWritter text="Supply: 2800" :changeable="true" class="text-7xl lg:text-9xl" />
    </div>
    <div class="content h-full w-full flex items-center justify-center">
      <TypeWritter text="Mint price: 0.0888 SOL" :changeable="true" class="text-7xl lg:text-9xl" />
    </div>
  </div>
  <section mx-auto min-h-screen flex flex-col items-center justify-center bg-zinc-900 px-8 py-8 container md:flex-row space-y-4 md:px-20 md:space-x-4 md:space-y-0>
    <div class="lg:w-1/3" mb-4 text-left>
      <img :src="logofull" alt="Logo">
    </div>
    <div class="z-50 my-4 whitespace-pre-line text-left font-bold font-sans lg:w-1/3">
      <h1 mb-4 text-3xl lg:text-6xl xl:text-6xl>
        Why Night Owl's?
      </h1>
      <p class="dis" mb-4 bg-stone-900 p-4 text-sm text-white lg:text-lg>
        You tell me.
      </p>
    </div>
  </section>

  <section min-h-screen flex items-center justify-center>
    <div class="flex items-center justify-center">
      <TypeWritter text="ONLY_FOR_TOKEN_HOLDER_AIRDROP" :changeable="true" class="text-4xl lg:text-6xl" />
    </div>
  </section>
  <TheNFT />
  <section min-h-screen flex items-center justify-center>
    <div class="flex items-center justify-center">
      <TypeWritter text="NEVER_SLEEP_GRIND_HARD_HOOT_HOOT" :changeable="true" class="text-4xl lg:text-6xl" />
    </div>
  </section>
</template>

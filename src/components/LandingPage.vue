<script setup>
import { onMounted, ref } from 'vue'

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

const sections = [
  { id: 1, text: '$NOWLS', changeable: true, class: 'text-4xl lg:text-7xl' },
  { id: 2, text: 'NFT + TOKEN ', changeable: true, class: 'text-4xl lg:text-7xl' },
  { id: 3, text: 'HOOT_HOOT', changeable: true, class: 'text-4xl lg:text-6xl' },
  { id: 4, text: 'NFT_SUPPLY: 2800', changeable: true, class: 'text-4xl lg:text-7xl' },
  { id: 5, text: '$NOWLS_SUPPLY: 28000000', changeable: true, class: 'text-4xl lg:text-7xl' },
  { id: 6, text: 'PUBLIC_PRICE: 0.13 SOL', changeable: true, class: 'text-4xl lg:text-7xl' },
  { id: 7, text: 'NEVER_SLEEP', changeable: true, class: 'text-4xl lg:text-6xl' },
]

const slider = sections.slice(0, 9)
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
  <!-- SLIDER -->
  <div class="h-screen flex flex-col gap-0 container md:gap-100">
    <template v-for="(section, index) in slider" :key="index">
      <div v-if="slider[0].text" class="content min-h-screen min-w-full flex items-center justify-center" :class="section.class">
        <TypeWritter :text="section.text" :changeable="section.changeable" />
      </div>
    </template>
  </div>

  <!-- Flexing 1 -->
  <!-- <section v-if="nonslider[0].text" class="min-h-screen flex items-center justify-center">
    <TypeWritter :text="nonslider[0].text" :changeable="nonslider[0].changeable" class="text-4xl lg:text-6xl" />
  </section> -->
  <!-- NFT Section -->
  <TheNFT min-h-screen @nft-section-visible="startAnimations" />
  <!-- Flexing 2 -->
  <!-- <section v-if="nonslider[1].text" class="min-h-screen flex items-center justify-center">
    <TypeWritter :text="nonslider[1].text" :changeable="nonslider[1].changeable" class="text-4xl lg:text-6xl" />
  </section> -->
</template>

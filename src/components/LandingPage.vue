<script setup>
import { onMounted, ref } from 'vue'
import logofull from '~/assets/owl.gif'

const title = ref('Welcome to Night Owls')
const paragraph = ref('A 2800 unique ready for hunting on Solana')
const letterDelay = ref(100)
const showParagraph = ref(false)
const showGif = ref(false)

onMounted(() => {
  setTimeout(() => {
    showParagraph.value = true
  }, 2000)

  setTimeout(() => {
    showGif.value = true
  }, 5000)
})
</script>

<template>
  <section class="min-h-screen flex items-center justify-center">
    <div flex flex-col items-center justify-center>
      <img v-if="showGif" class="mb-4 lg:w-1/3" :src="logofull" alt="Night Owls Logo">
      <h1 class="text-2xl lg:text-6xl md:text-4xl">
        <TypeWritter :text="title" :letter-delay="letterDelay" />
      </h1>
      <p v-if="showParagraph" class="text-sm lg:text-4xl md:text-2xl">
        <TypeWritter :text="paragraph" :letter-delay="letterDelay" />
      </p>
    </div>
  </section>
</template>

<script setup>
import { useRoute } from 'vue-router'

const route = useRoute()

const showRightArrow = route.path === '/'

const nextRoute = showRightArrow ? '/info' : ''
</script>

<template>
  <div class="route-controller fixed bottom-30 left-1/2 flex transform items-center justify-center gap-4 p-6 -translate-x-1/2">
    <router-link v-if="showRightArrow" :to="nextRoute" class="text-4xl transition-duration-100 ease hover:text-5xl hover:text-amber-600">
      <div i-carbon:arrow-right />
    </router-link>
  </div>
</template>

<style scoped>
/* Add any necessary styling */
</style>

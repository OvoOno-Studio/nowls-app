<script setup>
import { ref } from 'vue'
import daki from '~/assets/daky.png'
import goblin from '~/assets/goblin.png'
import bez from '~/assets/bez.png'

const team = [
  {
    name: 'bez',
    role: 'dev',
    image: bez,
  },
  {
    name: 'goblin',
    role: 'dev',
    image: goblin,
  },
  {
    name: 'daki',
    role: 'artist',
    image: daki,
  },
]

const tooltipActive = ref(false)
const tooltipText = ref('')
const tooltipTop = ref(0)
const tooltipLeft = ref(0)

function showTooltip(event, member) {
  tooltipActive.value = true
  tooltipText.value = `${member.name} - ${member.role}`
  updateTooltipPosition(event)
}

function hideTooltip() {
  tooltipActive.value = false
}

function updateTooltipPosition(event) {
  tooltipTop.value = event.clientY + 10
  tooltipLeft.value = event.clientX + 10
}

function filteredTeam(role) {
  return team.filter(member => member.role === role)
}
</script>

<template>
  <div class="min-h-screen flex flex-col items-center justify-center px-4">
    <h3 class="mb-8 text-3xl lg:text-6xl xl:text-6xl">
      Devs
    </h3>
    <section class="mb-8 flex items-center justify-center">
      <a href="https://twitter.com/bezmir369"><div i-carbon:logo-x icon-btn /></a>
      <div
        v-for="member in filteredTeam('dev')"
        :key="member.name"
        class="relative mb-4 ml-4 mr-4 h-30 w-30 overflow-hidden border-2 border-white rounded-full shadow-md transition duration-500 ease-in-out md:h-40 md:w-40 hover:scale-110 hover:shadow-xl"
        @mouseenter="showTooltip($event, member)"
        @mouseleave="hideTooltip"
      >
        <img :src="member.image" alt="Avatar" class="mt--7 rounded-full object-cover">
      </div>
      <a href="https://twitter.com/goblin_sensei"><div i-carbon:logo-x icon-btn /></a>
    </section>
    <h3 class="mb-8 text-3xl lg:text-6xl xl:text-6xl">
      Artist
    </h3>
    <section class="flex flex-col items-center justify-center gap-4">
      <div
        v-for="member in filteredTeam('artist')"
        :key="member.name"
        class="relative mb-4 mr-4 h-30 w-30 overflow-hidden border-2 border-white rounded-full shadow-md transition duration-500 ease-in-out md:h-40 md:w-40 hover:scale-110 hover:shadow-xl"
        @mouseenter="showTooltip($event, member)"
        @mouseleave="hideTooltip"
      >
        <img :src="member.image" alt="Avatar" class="mt--7 rounded-full object-cover">
      </div>
      <a href="https://twitter.com/DanzoRetsu"><div i-carbon:logo-x icon-btn /></a>
    </section>
    <transition name="fade">
      <div v-if="tooltipActive" class="absolute border border-gray-300 rounded-lg bg-white p-2 shadow-md" :style="{ top: `${tooltipTop}px`, left: `${tooltipLeft}px` }">
        <TypeWritter :text="tooltipText" class="text-gray-8" />
      </div>
    </transition>
  </div>
</template>

  <style scoped>
  .fade-enter-active,
.fade-leave-active {
  transition: transform 0.5s;
}
.fade-enter,
.fade-leave-to {
  transform: scale(0);
}
</style>

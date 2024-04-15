<script setup lang="ts">
import { ref } from 'vue'
import token from '~/assets/nowlsToken.png'

const socials = [
  { name: 'X', icon: 'i-carbon:logo-x', link: 'https://twitter.com/solananowls?s=21&t=7ujY1o2NLmeyKDdBZm-LdQ' },
  { name: 'X', icon: 'i-carbon:logo-discord', link: 'https://discord.gg/3HAHYXsgPy' },
]

const isMenuOpen = ref(false)

function toggleMenu() {
  isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
  <div class="sticky-nav-container z-90 flex justify-center">
    <nav sticky top-0 w-xl flex items-center justify-between rounded-0 bg-stone-9 px-8 py-2 md:rounded-b-full>
      <!-- Logo -->
      <router-link to="/" class="cursor-pointer hover:text-amber-600">
        <div :class="{ 'active-tab': $route.path === '/' }">
          <TheLogo w-10 />
        </div>
      </router-link>
      <!-- Info Tab -->
      <router-link to="/info" class="cursor-pointer hover:text-amber-600">
        <div :class="{ 'active-tab': $route.path === '/info' }">
          <div class="group relative cursor-pointer transition ease-in-out">
            <span class="md:text-amber-600">info</span>
            <span class="absolute inset-x-0 bottom-0 h-[2px] scale-x-0 transform bg-amber-600 transition-transform duration-300 ease-in-out group-hover:scale-x-100" />
          </div>
        </div>
      </router-link>
      <!-- Token Tab -->
      <router-link to="/token" class="cursor-pointer hover:text-amber-600">
        <div :class="{ 'active-tab': $route.path === '/token' }" class="flex items-center justify-center gap-4 text-sm">
          <div class="flex items-center justify-center gap-1">
            <div class="group relative cursor-pointer transition ease-in-out">
              <img :src="token" class="h-8 w-8">
              <span class="hidden md:text-amber-600">token</span>
              <span class="absolute inset-x-0 bottom-0 h-[2px] scale-x-0 transform bg-amber-600 transition-transform duration-300 ease-in-out group-hover:scale-x-100" />
            </div>
          </div>
        </div>
      </router-link>
      <!-- Mint Tab -->
      <router-link to="/mint" class="cursor-pointer hover:text-amber-600">
        <div :class="{ 'active-tab': $route.path === '/mint' }">
          <div class="group relative cursor-pointer transition ease-in-out">
            <span class="md:text-amber-600">mint</span>
            <span class="absolute inset-x-0 bottom-0 h-[2px] scale-x-0 transform bg-amber-600 transition-transform duration-300 ease-in-out group-hover:scale-x-100" />
          </div>
        </div>
      </router-link>
      <!-- Hamburger Icon for Mobile -->
      <div class="flex md:hidden">
        <button type="button" class="text-white hover:text-amber-600 focus:outline-none" aria-label="Toggle menu" @click="toggleMenu">
          <svg class="h-6 w-6 fill-current" viewBox="0 0 24 24">
            <!-- Hamburger Icon Path -->
            <path v-if="!isMenuOpen" fill-rule="evenodd" clip-rule="evenodd" d="M4 6h16v2H4V6zm0 5h16v2H4v-2zm0 5h16v2H4v-2z" />
            <!-- X Icon Path -->
            <path v-else fill-rule="evenodd" clip-rule="evenodd" d="M19.07 4.93a.75.75 0 010 1.06l-6.25 6.25 6.25 6.25a.75.75 0 11-1.06 1.06l-6.25-6.25-6.25 6.25a.75.75 0 01-1.06-1.06l6.25-6.25-6.25-6.25a.75.75 0 111.06-1.06l6.25 6.25 6.25-6.25a.75.75 0 011.06 0z" />
          </svg>
        </button>
      </div>
      <!-- Social Icons -->
      <div class="hidden gap-1 text-2xl md:flex">
        <a v-for="social in socials" :key="social.name" :href="social.link" icon-btn>
          <div i :class="social.icon" />
        </a>
      </div>
      <!-- Mobile Menu Content -->
      <transition name="slide">
        <div v-if="isMenuOpen" class="absolute left-0 right-0 top-full bg-stone-9 px-8 py-2 shadow-md md:hidden">
          <!-- Mobile: Social Icons -->
          <div class="flex justify-end gap-1 text-2xl">
            <a v-for="social in socials" :key="social.name" :href="social.link" icon-btn>
              <div i :class="social.icon" />
            </a>
          </div>
          <!-- End of Mobile: Social Icons -->
        </div>
      </transition>
      <!-- End of Mobile Menu Content -->
    </nav>
  </div>
</template>

<style scoped>
.active-tab {
  border-bottom: 2px solid #d87606;
}
.sticky-nav-container {
  position: sticky;
  top: 0;
}

.slide-enter-active,
.slide-leave-active {
  transition: transform 0.3s ease;
}

.slide-enter-to,
.slide-leave {
  transform: translateY(0);
}

.slide-enter,
.slide-leave-to {
  transform: translateY(-100%);
}
</style>

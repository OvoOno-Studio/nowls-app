<script setup lang="ts">
const socials = [
  { name: 'X', icon: 'i-carbon:logo-x', link: 'https://twitter.com/solananowls?s=21&t=7ujY1o2NLmeyKDdBZm-LdQ' },
  { name: 'X', icon: 'i-carbon:logo-discord', link: 'https://discord.gg/3HAHYXsgPy' },

]
</script>

<template>
  <nav sticky top-0 z-50 flex items-center justify-between px-8>
    <div>
      <TheLogo w-20 />
    </div>
    <div flex gap-1 text-2xl>
      <a v-for="social in socials" :key="social.name" :href="social.link" icon-btn>
        <div i :class="social.icon" />
      </a>
    </div>
  </nav>
</template>

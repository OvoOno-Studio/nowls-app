<script setup>
const socials = [
  { name: 'X', icon: 'i-carbon:logo-x', link: 'https://twitter.com/solananowls?s=21&t=7ujY1o2NLmeyKDdBZm-LdQ' },
  { name: 'X', icon: 'i-carbon:logo-discord', link: 'https://discord.gg/3HAHYXsgPy' },

]
</script>

<template>
  <nav class="flex flex-col items-center justify-center bg-stone-950 p-4">
    <!-- Social Items -->
    <div>
      <a v-for="social in socials" :key="social.name" :href="social.link" target="_blank" rel="noopener noreferrer" icon-btn>
        <div :class="`${social.icon} w-20 h-20`" />
      </a>
    </div>
    <a>
      <TheLogo class="w-20" />
    </a>
    <p class="text-sm font-mono hover:text-teal-100">
      © 2024 Night Owl's
    </p>
  </nav>
</template>
